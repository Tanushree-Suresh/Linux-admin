 # Project: Ubuntu Server Setup and Management on Azure
    
    This repository documents the step-by-step setup and configuration of an Ubuntu 22.04 LTS server on a Microsoft Azure Virtual Machine.
    
    ## Table of Contents
    
    1.  [Azure VM Setup](#1-azure-vm-setup)
    2.  [User Management](#2-user-management)
    3.  [Apache Web Server](#3-apache-web-server)
    4.  [UFW Firewall](#4-ufw-firewall)
    5.  [Automated Backups](#5-automated-backups)
    6.  [System Monitoring](#6-system-monitoring)
    7.  [Package Management](#7-package-management)
    
    ---
    
    ### 1. Azure VM Setup
    
    The virtual machine was created in the Azure Portal, and an SSH connection was established. Subsequently, the system was fully updated.
    
    **VM Details:**
    ![VM Details in Azure Portal](./screenshots/1_azure_portal/1.1_vm_details.png)
    
    **SSH Login & System Update:**
    ![Successful SSH Login](./screenshots/2_os_configuration/2.1_ssh_login.png)
    ![System Update Completed](./screenshots/2_os_configuration/2.2_system_update.png)
    
    ---
    
    ### 2. User Management
    
    A new non-root user (`demouser`) was created and added to the `sudo` group to perform administrative tasks securely.
    
    ![User Creation](./screenshots/3_user_management/3.1_user_creation.png)
    ![Sudo Privileges Verified](./screenshots/3_user_management/3.3_sudo_privileges.png)
    
    ---
    
    ### 3. Apache Web Server
    
    An Apache2 web server was installed to serve a [static website](./static-website/index.html). The permissions of the web root directory were set correctly.
    
    **Apache Status:**
    ![Apache Status Active Running](./screenshots/4_apache_setup/4.1_apache_status.png)
    
    **Result in Browser:**
    ![Static Website](./screenshots/4_apache_setup/4.2_website_display.png)
    
    ---
    
    ### 4. UFW Firewall
    
    The Uncomplicated Firewall (UFW) was configured to secure the server. Rules were added to allow inbound traffic for SSH (port 22) and 'Apache Full' (ports 80 & 443).
    
    ![UFW Status and Rules](./screenshots/5_firewall_ufw/5.1_ufw_status.png)
    
    ---
    
    ### 5. Automated Backups
    
    A [Bash script](./scripts/backup.sh) was created to back up the web directory `/var/www/html`. A daily cron job at 02:00 AM automates this process. Successes and failures are logged to `/var/log/backup.log`.
    
    **Cron Job Configuration and Test Run:**
    ![Crontab Setup](./screenshots/6_backups_cron/6.1_crontab_setup.png)
    ![Manual Backup Execution](./screenshots/6_backups_cron/6.2_backup_execution.png)
    
    ---
    
    ### 6. System Monitoring
    
    Standard Linux tools are used to monitor system resources and analyze log files for troubleshooting.
    
    **Resource Usage (`top`, `free`, `df`):**
    ![top output](./screenshots/7_system_monitoring/7.1_top_output.png)
    ![free -h output](./screenshots/7_system_monitoring/7.2_free_output.png)
    ![df -h output](./screenshots/7_system_monitoring/7.3_df_output.png)
    
    **Log Analysis:**
    ![Apache Error Log](./screenshots/7_system_monitoring/7.4_log_analysis.png)
    
    ---
    
    ### 7. Package Management
    
    Automatic security updates were configured using `unattended-upgrades` to help keep the system secure.
    
    ![Configuring unattended-upgrades](./screenshots/8_package_management/8.1_auto_updates.png)


