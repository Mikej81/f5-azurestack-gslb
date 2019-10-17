# GSLB ARM templates for Azure Stack

Templates developed to provide Global Service Load Balancing across Azure Stack Scale Units.

* Post Install Configurations to BIG-IP
  * Each stack should only take about 20 minutes to complete.
  ![alt text](/images/1.png "deployment time")
  * (OPTIONAL) Device Cert Update https://support.f5.com/csp/article/K15664
  * Enable root account to establish trust https://support.f5.com/csp/article/K13121, once the trust (certificate exchange) is established, the root account can be disabled again.
  * Weird Issue with default routes.  Remove from stack 2 and all good.
  * Create DNS Sync Group https://f5-dns-automation-demo-12-1-x.readthedocs.io/en/latest/lab2/sync-group.html
  ![alt text](/images/5.png "datacenters")![alt text](/images/6.png "servers")

* Post Install Configurations to Azure Stack NSG's (lock down source IP)
  * Initial deployment includes allow 22 on external interface, this can and should be removed after trust is established.
  * Initial deployment does not block source on NSG's, this should be changed once everything is online.  Management NSG should be locked to management source, External (4353/TCP) NSG should be locked to the other scale unit for sync.  443 should also be locked until applications with Virtual Servers are deployed.
  ![alt text](/images/3.png "cleaned up")
