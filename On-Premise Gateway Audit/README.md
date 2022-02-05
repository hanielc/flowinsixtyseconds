# On-Premise Gateway Audit
This solution is provided as-is with no support or warranties.

The purpose of this solution is to provide a way to determine which gateways are used in specific Power Platform connections and Power Automate flows.  It should be installed in an environment and used with an account that has Power Platform Admin role.

In order to get the list of gateways, you must levergate the DataGateway PowerShell module as follows:
1. Open PowerShell 7 window (if you don't have it installed, you can download it from [Install PowerShell on Windows](https://docs.microsoft.com/en-us/powershell/scripting/install/installing-powershell-on-windows?view=powershell-7.2)
2. Install the DataGateway module:  ```Install-module DataGateway -Force```
3. Connect to the data gateway using an account that has Power Platform Admin role: ```Connect-DataGatewayServiceAccount```
4. Get a list of all gateways: ```Get-DataGatewayCluster -Scope Organization | ConvertTo-Json -Depth 10 | Add-Content -Path c:\temp\gateways2.json```

You will be refering to this file in the Gateway section of the app.
