# Sella database connectivity incidence report

The following is the incident report for Sella website outage that occured on 4th january, 2024. We understand that this issue affected most of our visitors and resellers who use our database.

**Issue Summary**

From **6:17PM - 6:48PM**, visitors to our website experienced a **database error**. This affected all services that require the database data, including the correct rendering of all the shop pages and data. All clients who visited the site could not go past the database error being displayed on the screen. Vendors could also not post their products on the site do to the loss of the connectivity. The root cause of the outage was a database change that was not implemented on the configuration file.

**Timeline**

* 6:17 PM: Database switch begins
* 6:25 PM: Outage begins
* 6:29 PM: First complaint from vendor to the team
* 6:35 PM: Escalation to senior developer team PM
* 6:40 PM: Reverted to previous database
* 6:47 PM: Configuration to new database redone
* 7:00 PM: Server restarted
* 7:05 PM: All systems restored

### Root Cause

At 6:17 PM EAT, a database that has been under construction for sometime now was pushed to production. The change was on the phpmyadmin server but failed to reflect the change to the database on the config.php file. This caused a database connection error since the config file was pointing to a non-existent database. At 6:35 PM, the issue was escalated to the project manager, who directed the team to revert to the previous database before the configuration was redone. 6:47 PM, the team then made the changes on the config file to point to the correct database and successful transfer was done, restoring all the services.

### Corrective and preventative measures 

Since we encountered the outage, we have conducted an extensive analysis on the outage and come up with a clear mitigation strategy. The following are the corrective and preventative measures taken to avoid a repeat of the error:

* We have come up with  a solid framework that will be followed while conducting such changes on all layers of our tech stack.

* We have established a clear communication strategy in order to know who answers to who and provide accountability.

* A testing environment will be provided so as to test the updated scenario on a non-public-facing  web app first before deploying on the production environment.

Sincerely,

Sella Web Infrastructure Team








