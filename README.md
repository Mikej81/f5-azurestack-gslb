# GSLB ARM templates for Azure Stack

Templates developed to provide Global Service Load Balancing across Azure Stack Scale Units.

* Post Install Configurations to BIG-IP
  * Each stack should only take about 20 minutes to complete.
  ![alt text](/images/1.png "deployment time")
  * (OPTIONAL) Device Cert Update [https://support.f5.com/csp/article/K15664](https://support.f5.com/csp/article/K15664)
  * Enable root account to establish trust [https://support.f5.com/csp/article/K13121](https://support.f5.com/csp/article/K13121), once the trust (certificate exchange) is established, the root account should be disabled.
  * Create DNS Sync Group [https://f5-dns-automation-demo-12-1-x.readthedocs.io/en/latest/lab2/sync-group.html](https://f5-dns-automation-demo-12-1-x.readthedocs.io/en/latest/lab2/sync-group.html)
  * (OPTIONAL) Create Device SyncOnly Group [https://support.f5.com/csp/article/K63243467](https://support.f5.com/csp/article/K63243467)
  ![alt text](/images/5.png "datacenters")![alt text](/images/6.png "servers")

* Post Install Configurations to Azure Stack NSG's (lock down source IP)
  * Initial deployment includes allow 22 on external interface, this can and should be removed after trust is established.
  * Initial deployment does not block source on NSG's, this should be changed once everything is online.  Management NSG should be locked to management source, External (4353/TCP) NSG should be locked to the other scale unit for sync.  443 should also be locked until applications with Virtual Servers are deployed.
  * GTM_DNS Rule is set to allow port 53 (DNS) traffic in, and BIG-IP resolver will start working once Listeners are created.
  ![alt text](/images/3.png "cleaned up")

## Troubleshooting
  * iQuery [https://support.f5.com/csp/article/K13690](https://support.f5.com/csp/article/K13690)

## Support guide
This project is community supported and not supported by F5 Support.

To report defects and security vulnerabilties, or submit enhancements and general questions open an issue within the GitHub repository.

1. In the top-right corner, expand :heavy_plus_sign: **More**, and then select **New Issues** from the list.
2. Enter a title, a description, and then click **Submit new issue**.

## Contributor License Agreement
Individuals or business entities who contribute to this project must have completed and submitted the F5 Contributor License Agreement.