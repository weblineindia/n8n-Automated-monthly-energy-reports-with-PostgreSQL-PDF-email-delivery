
# Automated Monthly Energy Reports with PostgreSQL, PDF.co & Email Delivery

This workflow automatically collects monthly energy generation data from a PostgreSQL database, converts it into a structured PDF report, and emails it to stakeholders. It removes manual report creation and ensures timely, consistent delivery of performance summaries.

---

## Who’s It For

* Energy companies monitoring solar, wind, or hydro generation
* Operations & maintenance (O&M) teams needing monthly summaries
* Managers and executives requiring periodic performance reports
* Data analysts who want automated reporting instead of manual exports

---

## How It Works

1. **Monthly Trigger**
   Schedules the workflow to run once every month.

2. **PostgreSQL Node**
   Fetches energy generation data from the `energy_data` table.

3. **Code Node (Data Transformation)**
   Structures raw records into a clean JSON format including metadata such as:

   * Date range
   * Aggregated records
   * Notes or annotations

4. **HTTP Request (PDF.co API)**
   Converts structured data into a professionally formatted PDF report.

5. **Gmail Node (Email Delivery)**
   Sends the generated PDF (or a download link) to configured recipients.

---

## How to Set Up

1. Import the workflow JSON into your n8n instance
2. Configure credentials:

   * PostgreSQL (host, database, user, password, schema)
   * Gmail OAuth2
   * PDF.co API key
3. Update:

   * Database table name (`energy_data`)
   * Email recipients in the Gmail node
   * PDF template or HTML layout (if custom branding is required)
4. Activate the workflow

---

## Requirements

* n8n (cloud or self-hosted)
* PostgreSQL database with energy generation data
* PDF.co account with a valid API key
* Gmail account with OAuth2 access
* Internet access for API calls

---

## How to Customize

* Modify the SQL query to filter:

  * Specific plants
  * Locations
  * Custom date ranges
* Enhance the Code node to calculate:

  * Average output
  * Performance trends
  * Anomalies
* Use a custom HTML template in PDF.co for branded reports
* Replace Gmail with Outlook, SMTP, Slack, or Teams for delivery

---

## Add-Ons

* Slack or Microsoft Teams notifications when reports are sent
* Store generated PDFs in Google Drive or Amazon S3 for archival
* Add dashboards (Grafana, Superset) using the same database
* Auto-create Jira tasks when performance thresholds are crossed

---

## Use Case Examples

* Solar companies emailing monthly production reports to plant owners
* Wind farm operators generating regulatory compliance reports
* O&M teams automating KPI summaries for executives
* Consulting firms managing multi-client energy reporting

---

## Common Troubleshooting

| Issue                     | Possible Cause                           | Solution                                           |
| ------------------------- | ---------------------------------------- | -------------------------------------------------- |
| Workflow does not trigger | Schedule trigger misconfigured           | Verify the trigger is set to run monthly           |
| No data from PostgreSQL   | Incorrect schema, table, or credentials  | Check DB connection details and table name         |
| PDF not generated         | Missing or invalid PDF.co API key        | Regenerate API key and update n8n credentials      |
| Email not sent            | Gmail OAuth expired or invalid recipient | Reconnect Gmail and confirm recipient addresses    |
| PDF output malformed      | Incorrect JSON or HTML formatting        | Review Code node output and PDF.co request payload |

---

## Need Help?

Our **n8n workflow automation experts at WeblineIndia** can help you:

* Securely configure PostgreSQL connections
* Design branded, professional PDF templates
* Add delivery channels (Slack, Teams, S3)
* Extend reporting with KPIs, charts, and anomaly detection
* Scale workflows for enterprise reporting needs

---
