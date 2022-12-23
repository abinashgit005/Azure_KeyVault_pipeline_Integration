# Azure_KeyVault_pipeline_Integration
1) Create Azure Key Vault with Secrets and persmissions.
![choose rbac](snap1.jpg)
2) Assign RBAC role to users such as keyvault Secret Officer 
create a SPN(Service Principle Name) and assign role "Key Vault Secret User"
![Add keyvault secret officer and user](snap2.jpg)

    run the below command in azure cloudshell.
    ```
    az ad sp create-for-rbac -n "my spn name"
    ```
    you will get the outputas below.
    ```
    The output includes credentials that you must protect. Be sure that you do not include these credentials in your code or check the credentials into your source control. For more information, see https://aka.ms/azadsp-cli
    {
    "appId": "403f91a4-d365-4776-b69d-761cxxxxxxxx",
    "displayName": "spn-keyvault-devops",
    "password": "8A78Q~OsWiMiEZ9EWUyCHrxvsj_Ecxxxxxxxxxx",
    "tenant": "df77f402-7f2e-47d2-bea6-e90xxxxxxxx"
    }

    ```

3) create a service connection in Dev.azure.com \
Project setting >> Service connection >> choose "Manual" \
provide "Service Principal Id", "Service principal key", "Tenant_ID" \
allow for all Pipeline and submit.