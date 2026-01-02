# Automated Monthly Energy Reports with PostgreSQL, PDF.co & Email Delivery

This workflow automatically collects monthly energy generation data from a PostgreSQL database, converts it into a structured PDF report, and emails it to stakeholders. It eliminates manual report creation and ensures timely delivery of performance summaries. :contentReference[oaicite:1]{index=1}

---

## Who’s It For

- Energy companies monitoring solar, wind or hydro generation
- Operations & maintenance (O&M) teams needing monthly summaries
- Managers and executives requiring periodic performance reports
- Data analysts who want automated reporting instead of manual exports :contentReference[oaicite:2]{index=2}

---

## How It Works

1. **Monthly Trigger** — Schedules the workflow to run once a month.
2. **PostgreSQL Node** — Fetches energy data from the `energy_data` table.
3. **Code Node (Transform Data)** — Structures the raw records into JSON with metadata such as `date_range`, `records`, and `note`.
4. **HTTP Request (PDF.co API)** — Converts the structured data into a formatted PDF report.
5. **Gmail Node (Send Report)** — Sends the PDF report (or link) via email to the configured recipient. :contentReference[oaicite:3]{index=3}

---

## How to Set Up

1. Import the workflow JSON into your n8n instance.
2. Configure credentials:
   - PostgreSQL connection (DB host, user, password, database, schema).
   - Gmail OAuth2 credentials.
   - PDF.co API key (for HTML → PDF conversion).
3. Update the following:
   - Database table (`energy_data`).
   - Email recipients in the Gmail node.
   - PDF template (if custom formatting is required).
4. Activate the workflow. :contentReference[oaicite:4]{index=4}

---

## Requirements

- n8n (self-hosted or cloud)
- PostgreSQL database with energy generation data
- PDF.co API account with a valid API key
- Gmail account with OAuth2 access
- Internet access for API calls :contentReference[oaicite:5]{index=5}

---

## How to Customize

- Change the SQL query in the PostgreSQL node to filter specific plants or date ranges.
- Update the Code node to add extra fields (e.g., average power, anomalies).
- Modify the PDF.co API request body to use a custom HTML template for branding.
- Replace Gmail with Outlook, SMTP, or Slack for report distribution. :contentReference[oaicite:6]{index=6}

---

## Add-Ons

- Add a Slack or Microsoft Teams node to notify teams when reports are sent.
- Store generated PDFs in Google Drive or Amazon S3 for archival.
- Add a dashboard (e.g., Grafana or Superset) that references the same database for a real-time view.
- Integrate with Jira to auto-create tasks for alerts based on performance thresholds. :contentReference[oaicite:7]{index=7}

---

## Use Case Examples

- Solar company emailing monthly energy production reports to plant owners.
- Wind farm operator generating regulatory compliance reports.
- O&M teams automating KPI summaries for executives.
- Consulting firms monitoring multiple clients’ energy production. :contentReference[oaicite:8]{index=8}

---

## Common Troubleshooting

| Issue                            | Possible Cause                             | Solution                                           |
| -------------------------------- | ------------------------------------------ | -------------------------------------------------- | ------------------------------------- |
| Workflow does not trigger        | Cron not set correctly                     | Verify `Schedule Trigger` node interval is monthly |
| No data returned from PostgreSQL | Wrong schema/table or DB credentials       | Check DB connection settings and table name        |
| PDF not generated                | Invalid or missing PDF.co API key          | Generate a new key and update credentials          |
| Email not sent                   | Gmail OAuth expired or incorrect recipient | Reconnect Gmail and confirm recipient address      |
| PDF output malformed             | Incorrect JSON → HTML conversion           | Check Code node formatting and PDF.co request body | :contentReference[oaicite:9]{index=9} |

---

## Need Help?

Our n8n workflow automation experts at **WeblineIndia** can help you:

- Set up the PostgreSQL connection securely,
- Customize the PDF layout with your company branding,
- Add more delivery channels (Slack, Teams, S3),
- Extend reporting logic (KPIs, charts, anomaly detection),
- And so much more. :contentReference[oaicite:10]{index=10}
