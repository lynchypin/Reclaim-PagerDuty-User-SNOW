This runs a short script directly in ServiceNow whenever a user is marked inactive (whether by Entra ID, LDAP, or an admin).

In ServiceNow, search for **System Definition > Business Rules** and click **New**.

### Configure the Business Rule:

* **Name:** Deprovision PagerDuty User on Deactivation
* **Table:** User (`sys_user`)
* **Active:** Checked
* **Advanced:** Checked

### In the "When to run" tab:

* **When:** after
* **Insert / Update:** Check *Update*
* **Filter Conditions:** `Active` changes to `false` **AND** `PagerDuty ID` (`x_pd_integration_pagerduty_id`) is not empty.

### In the "Advanced" tab:

Paste the script.
