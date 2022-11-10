# S-Teams-Approval-Router
 This solution is to visualize how to route approvals from differrent systems to Teams Approvals.
 
 TO-DO:
 
You can remove Azure Key Vault actions.

When you will import solution you need to establish connection with Azure Key Vault.

I am using this mechanism to restrict HTTP triggered flow by using below trigger condition:

@equals(triggeroutputs()['headers']['secret'],' your_Azure_Key_Vault_secret_value ')

Degree of paralelism is set to 1 to prevent from running concurrent flow run.
 
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
