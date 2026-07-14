## Quick Overview

This workflow monitors Gmail for new unread emails, uses Google Gemini to classify each email’s intent, then creates Gmail draft replies and Slack alerts for questions/requests, escalates complaints with Slack and Google Tasks, and logs FYI and spam activity to Google Sheets.

## How it works

1. Triggers when a new unread email arrives in Gmail.
2. Extracts the sender, subject, body text, and message ID, then bundles incoming emails for batch processing.
3. Sends the bundled emails to Google Gemini to classify each message as **Question**, **Request**, **Complaint**, **FYI**, or **Spam** and to generate the required action payloads.
4. Parses Gemini’s JSON response, splits it back into one item per email, and routes each email by its classified intent.
5. For **Question** or **Request** emails, creates a Gmail draft reply, posts a Slack notification with a preview, and logs the action to Google Sheets.
6. For **Complaint** emails, posts an urgent Slack alert, creates a high-priority follow-up in Google Tasks, and logs the action to Google Sheets.
7. For **FYI** and **Spam** emails, skips external actions and logs the outcome to Google Sheets.

## Requirements to Use This Workflow

- [**n8n account** (Self-hosted or Cloud)](https://n8n.partnerlinks.io/om1efg2qgvwi)
- **Gmail** account with OAuth2 credentials
- **Google Gemini API** credentials for AI-powered email classification
- **Slack** workspace with OAuth2 credentials
- **Google Sheets** account with OAuth2 credentials for activity logging
- **Google Tasks** account with OAuth2 credentials for complaint follow-ups
- Basic understanding of **n8n workflows** and Google Workspace integrations

## Setup

1. Connect credentials for Gmail OAuth2, Google Gemini (PaLM) API, Slack OAuth2, Google Sheets OAuth2, and Google Tasks OAuth2.
2. Update the Gmail trigger settings and mailbox access to match the account and unread-email behavior you want to monitor.
3. Set the target Google Sheets document and ensure it has columns for **Timestamp**, **Email ID**, **Sender**, **Subject**, **Intent**, and **Action**.
4. Select the Slack channels for general notifications and urgent complaint alerts.
5. Choose the Google Tasks list and update the task list ID used for complaint follow-ups.

## Need Help?

If you need assistance setting up this workflow, customizing it for your email operations, or building advanced AI-powered automation, our team at **WeblineIndia** is here to help.

We can assist you with:

- Workflow setup and customization
- Google Gemini integration and prompt optimization
- Gmail, Google Sheets, Slack, and Google Tasks integrations
- AI-powered email classification and routing
- Business process automation and workflow optimization
- Enterprise-grade automation solutions
- Custom n8n workflow development

**Useful Resources:**

- **Contact Us:** https://www.weblineindia.com/contact-us.html
- **n8n Automation Services:** https://www.weblineindia.com/n8n-automation/
- **Process Automation Solutions:** https://www.weblineindia.com/process-automation-solutions.html
- **Hire n8n Developers:** https://www.weblineindia.com/hire-n8n-developers/

Our experts can help you build, customize, and scale intelligent automation workflows tailored to your business requirements.
