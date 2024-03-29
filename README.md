# Ghost Deployment Script
Automate your Ghost installation using this deployment script powered by Docker and Bash. Enhance the security of your Ghost instance with just one command.

Whether you're working with a fresh server or an existing setup, this script is designed for both new and veteran Ghost admins.


# About Ghost

Ghost is a free and open source independent technology suite for modern publishing, memberships, subscriptions and newsletters.

## Features

- 🚀 One-command deployment.
- 🔐 Enhancements to server security (SSH port change, firewall setup, Fail2Ban integration).
- 📘 Open-source and redistributable (a credit and shout out to Honeytree Technologies is greatly appreciated).

## Script Details

- **Language**: Bash
- **Deployment**: Docker-based Ghost installation.
- **Configuration Options**:
  - Automatic SSL certificate creation using Let's Encrypt along with Nginx configuration.

## Requirements

- Server or VPS with minimum 4GB RAM, 2 vCPU, and 65 GB storage.
- Ubuntu v20.04 LTS.
- Open ports:  443, 80 and SSH (Which you will choose in the script).
- Active internet connection to fetch packages and Docker images.
- Domain name pointing to the server's IP address (necessary for SSL certification).
- An email delivery service or SMTP server.

## Installation Steps

1. SSH into the machine and assume root privileges.
2. Create and navigate to a directory: `mkdir auto_script && cd auto_script`.
    You can also use own directory.
3. Run the following command to start the script.
    ```bash
    curl -sSL https://code.honeytreetech.com/fediverse/ghost/auto-installer/ghost_auto_script.sh -o ./ghost_auto_script.sh && sudo chmod +x ghost_auto_script.sh && ./ghost_auto_script.sh
    ```
4. Follow further on-screen instructions to complete the setup.
5. You will be prompted for installation details per the following table.
    | Name | Description | Mandatory | Optional | Default Value | 
    |------|---------|-----------|----------|---------------|
    |`admin_user`|Admin user name| &checkmark; | &#10006;| &#10006; | 
    |`admin_email` | Admin email| &checkmark;| &#10006;| &#10006;|
    |`admin_password` | Admin password| &checkmark;| &#10006;| &#10006;|
    |`site_title` | Site title| &checkmark;| &#10006;| &#10006;|
    |`domain_name` | Domain name| &checkmark;| &#10006;| &#10006;|
    |`smtp_transport` | SMTP transport| &checkmark;| &#10006;| &#10006;|
    |`smtp_host` | SMTP host| &checkmark;| &#10006;| &#10006;|
    |`smtp_port` | SMTP port| &checkmark;| &#10006;| &#10006;|
    |`smtp_user` | SMTP user| &checkmark;| &#10006;| &#10006;|
    |`smtp_password` | SMTP password| &checkmark;| &#10006;| &#10006;|
    |`smtp_from_address` | SMTP from address| &checkmark;| &#10006;| &#10006;|
    |`db_user` | Database user| &checkmark;| &#10006;|ghost |
    |`db_root_password` | Database  Root Password | &checkmark;| &#10006;| &#10006;|
    |`db_password` | Database Password|&checkmark;| &#10006;|pass_XXXXXXXXX (whereX is Random character) |
    |`db_name` | Database name|  &checkmark;| &#10006;|ghost_XXXXXXXXX (whereX is Random character) |&checkmark;
    |`port` | SSH port | &checkmark;| &#10006;| &#10006;|

                                
5. Accept terms of service as prompted.
6. Follow further on-screen instructions to complete the setup.

## Post Deployment

- Ghost via the provided domain with the given admin credentials.
- SSH port defaults to new port (which you entered in the script).
- fail2ban is activated with progressive blocking.

## Post-Installation Security Recommendations

Once you have successfully deployed Ghost using this script, it's crucial to take additional steps to secure and harden your environment. 

Consider the following actions:

- **Regular Updates**: Ensure that all system packages and software are regularly updated to patch potential vulnerabilities.
- **Firewall Configuration**: Fine-tune your firewall settings to allow only necessary traffic and block potential threats.
- **User Access**: Limit or disable root access. Use sudo for administrative tasks and avoid using the root account for daily tasks.
- **Secure Passwords**: Implement strong password policies, and consider using password managers.
- **Two-Factor Authentication**: Where possible, enable 2FA for critical services and accounts.
- **Backup**: Regularly back up critical data and ensure backups are stored securely.
- **Monitoring & Logging**: Set up monitoring and logging to detect and alert on suspicious activities.
- **Application-Specific Security**: Explore and implement security best practices specifically tailored to Ghost and any other applications you might be running.
- **Review and Audit**: Periodically review and audit your security settings and practices to ensure they are up-to-date with the latest threats and vulnerabilities.

It's essential to recognize that the security landscape is dynamic. Stay informed, and be proactive in securing your digital assets.



## Disclaimer
Using the installer is solely at your own risk, and you are responsible for any issues regarding quality, performance, accuracy, and effort. Additionally, support is only available to managed services clients of [Honeytree Technologies, LLC](https://honeytreetech.com); no free support is provided.

## Credits

A big thank you to [Honeytree Technologies, LLC](https://honeytreetech.com) for making this script possible.

Stay connected with us on Ghost: [@jeff@honeytree.social](https://honeytree.social/@jeff).
