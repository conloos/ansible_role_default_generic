# Ansible Role for configure all linux systems.

**summary**
This role is a generic role for basic configuration of all linux systems.
Look in the tasks directory for each configuration.
All configurations are held atomically via their own files. 

## Variables that have to be defined

### Automated Certificate Management Environment (acme)
| variable | required | description |
| -------- | ---------| ----------- |
| tls_cert_contact | False | Email-address of the cert contact |
| acme_fqdn | False | fqdn to the CA server |
| acme_url | False | url to the CA server |
| acme_fingerprint | False | fingerprint of the root certificate |

### import certificates
| variable | required | description | example |
| -------- | ---------| ----------- | ------- |
| crt_zip_download_url | no | Import certificates as zip and install in system certificate store. | |
### Network Time - timesyncd
| variable | required | description |
| -------- | ---------| ----------- |
| ntp_server | False | IP address of the ntp-server (udp 123) default: pool.ntp.org |

### sssd
| variable | required | description | example |
| -------- | ---------| ----------- | ------- |
| sssd_computerou | False | LDAP path to the ou where the computerobjects are stored. E.G:  "OU=Linux,OU=Server,DC=Example,DC=com" | |
| realm | False | Realm to use for join. If none provided, try to autodiscover. | |
| sssd_permitted_users | False | List of AD users who are allowed to log in. If no users or groups are defined, **all** AD accounts are allowed to login. | sssd_permitted_users: [john@example.com] |
| sssd_permitted_groups | False | List of AD groups who are allowed to log in. If no users or groups are defined, **all** AD accounts are allowed to login. | sssd_permitted_groups: [ adm, "domain admins@bodomos.lan"] |
| vault_AD.administrator_user | True | User to Join Object ||
| vault_AD.administrator_password | True | Password for the User ||

### sshd
| variable | required | description |
| -------- | ---------| ----------- |
| sshd_allowgroups | False | Space separated list of groups allowed to connect to the server. **Dont forget** to add the allowed local groups.|

### sudoers
| variable | required | description | example |
| -------- | ---------| ----------- | ------- |
| sudo_users | False | At the moment only 'ALL=(ALL) ALL' supported. | sudo_users: [john@example.com] |
| sudo_groups | False | At the moment only 'ALL=(ALL) ALL' supported. | sudo_groups: ["domain admins@bodomos.lan"] |
