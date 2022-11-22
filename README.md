# S-Teams-Approval-Router
 This solution is to visualise how to route approvals from different systems to Teams Approvals.

Remember that if you want to use it in production most likely it will be considered MULTIPLEXING so I highly recommend to buy relevant license for running this flow. When I was writing this comment relevant license was Power Automate per flow plan.

https://learn.microsoft.com/en-us/power-platform/admin/powerapps-flow-licensing-faq
 
 TO-DO:
 
You can remove Azure Key Vault actions.

When you will import solution you need to establish connection with Azure Key Vault.

I am using this mechanism to restrict HTTP triggered flow by using below trigger condition:

@equals(triggeroutputs()['headers']['secret'],' your_Azure_Key_Vault_secret_value ')

Degree of paralelism is set to 1 to prevent from running concurrent flow. This option once turned on can't be turned off so you can only change degree. Maximum value is 100 this mean that at the same time you will not be able to run more than 100 parallel approval flows which is ok in development but it should not be turned on in production.
 
Please save flows:
 
  Approval Router flow
  
  Source System receiver
 
to get URL address to use them in Environment Variables:
 
  Approval Router flow > Trigger input from sample service HTTP URI
  
  Source System receiver > Source System receiver HTTP POST URL
 
Environment Variable "Application Owner email" - user with provided email will be notified that there is missing scenario - new SourceSystem.

If Approval Solution is not installed in your Environment please read below webpage:

https://support.microsoft.com/en-us/topic/power-automate-approvals-provisioning-overview-and-troubleshooting-2306313a-49fa-efde-c716-a34c573ec942

Approval / Adaptive Card / Email / Approval webpage - all of them will be updated regardless of the response source.

https://learn.microsoft.com/en-us/power-automate/approvals-known-issues

https://learn.microsoft.com/en-us/power-automate/overview-adaptive-cards

https://learn.microsoft.com/en-us/power-automate/metadata-update-sample
