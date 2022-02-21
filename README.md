# Ansible Role for configure all linux systems.

**summary**
This role is a generic role for basic configuration of all linux systems.
Look in the tasks directory for each configuration.
All configurations are held atomically via their own files. 

## Variables that have to be defined
First look at tasks/0_check.yml

| variable | description |
| -------- | ----------- |
| tls_cert_contact | Email-address oft the cert contact |
| ca.fqdn | fqdn to the ca server |
| ca.url | url to the ca server |
| ca.fingerprint | fingerprint of the root certificate |

