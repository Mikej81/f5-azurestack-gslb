# GSLB ARM templates for Azure Stack

Templates developed to provide Global Service Load Balancing across Azure Stack Scale Units.

- Post Install Configurations to BIG-IP
 -- (OPTIONAL) Device Cert Update https://support.f5.com/csp/article/K15664
 -- Enable root account to establish trust https://support.f5.com/csp/article/K13121
 -- Issue with default routes.  remove from stack 2 and all good.
 -- Create DNS Sync Group https://f5-dns-automation-demo-12-1-x.readthedocs.io/en/latest/lab2/sync-group.html

- Post Install Configurations to Azure Stack NSG's (lock down source IP)
