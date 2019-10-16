# GSLB ARM templates for Azure Stack

Templates developed to provide Global Service Load Balancing across Azure Stack Scale Units.

- Post Install Configurations to BIG-IP
 - (OPTIONAL) Device Cert Update https://support.f5.com/csp/article/K15664
 - ConfigSync Configuration Local Address 
 - issue with cert trusts?  https://support.f5.com/csp/article/K13823 
 - issue with disabled root account https://support.f5.com/csp/article/K13121
 - Create DNS Sync Group https://f5-dns-automation-demo-12-1-x.readthedocs.io/en/latest/lab2/sync-group.html
- Post Install Configurations to Azure Stack NSG's (lock down source IP)