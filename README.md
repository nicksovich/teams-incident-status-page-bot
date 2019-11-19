# Reindeer Systems Status Updates

![Reindeer](https://jhandcdn.blob.core.windows.net/blob/reindeer.gif)

## Deployment Instructions:

The blue button below will deploy all resources needed for this solution in to the Resource Group and Azure region of your choice. The name you choose also determines the URL used to view the Status Page as well as the incoming URL used to trigger updates.

---

## Follow These Steps:

1. Create the Azure Function app, Storage account, and SignalR Service with this button: [![Deploy to Azure](https://azuredeploy.net/deploybutton.svg)](https://azuredeploy.net/)

>This will begin deploying everything needed for the solution and will provide a link to the public facing URL of the Status Pagea as well as a link to your new resource group where you will continue with step 2.

---

2.  In the Azure portal, open the Storage account and add a table named `statuses`. You do not need to set any properties or add records.

    ![Create table](CreateStatusesTable.gif)

---

3. Navigate to the function app, and open the `teams-webhook` function. Click "Get Function URL" and copy the URL.

---

1. Last, open Teams and navigate to the "Apps" page of the team in which you want to create the bot. Click "Create outgoing webhook".

    - Use `StatusPage` as the bot name (this is hardcoded, for now). 
    - Paste in the function URL, and enter a description and press the create button.

    > You will be prompted with a secret code for validating webhook calls from Teams. We currently do not use this. Close the dialog box.

    ![Create outgoing webhook](Webhook.gif)    

    ![Reindeer2](https://jhandcdn.blob.core.windows.net/blob/reindeer3.gif)

2. Open Teams and update the status page by typing `@StatusPage` to summon the bot followed by `open We are experiencing a problem. Standby for more information`

## Final Result should look like this

![Reindeer2](https://jhandcdn.blob.core.windows.net/blob/reindeer2.gif)

![Reindeer Updates](ReindeerUpdates.gif)
