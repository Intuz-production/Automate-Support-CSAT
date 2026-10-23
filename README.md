*Intuz — Your automation partner, one workflow at a time.*

<p align="center">
  <picture>
    <img alt="Banner Image" src="https://github.com/user-attachments/assets/210f97fc-0fce-404a-b647-7dfe1302cd37" />
  </picture>
</p>

[Intuz](https://www.intuz.com) helps organizations orchestrate AI, automation, and enterprise systems through scalable workflows. Our repository showcases proven implementations across healthcare, operations, customer support, document processing, sales, and back-office functions, enabling teams to accelerate automation initiatives without starting from scratch.

[N8N Creator](https://n8n.io/creators/intuz/) · [AI Automation Agency](https://www.intuz.com/company/) · [Generative AI Development Company](https://www.intuz.com/generative-ai-development/) · [For Custom Workflow Automation](https://www.intuz.com/get-started/)

# Close the support loop and send CSAT between Jira, Gmail, WhatsApp and HubSpot

## Quick overview

This workflow closes the loop on Jira support tickets by sending customer auto-replies and CSAT requests via WhatsApp (WAHA) or Gmail, then saving CSAT responses back to Jira and optionally logging notes to HubSpot.

## How it works

1. Receives a new ticket payload from another n8n workflow run, loads the close-loop configuration, and normalizes the message details for the customer’s channel.
2. Checks whether an acknowledgement can be sent, then sends the auto-reply via WAHA WhatsApp API or Gmail.
3. Optionally creates a HubSpot note (and associates it to the contact) when a HubSpot contact ID is provided.
4. Adds a Jira comment and label to mark that the customer auto-reply was sent.
5. Receives a Jira webhook when an issue transitions to (or is in) Done, validates a shared token, and skips tickets that already have a CSAT-sent label.
6. Fetches the Jira issue to determine channel and contact details, builds a CSAT form link, and sends the CSAT request via WAHA WhatsApp API or Gmail.
7. Adds a Jira comment and label to record that the CSAT request was sent, then accepts CSAT form submissions, writes the score (and optional custom field) to Jira, and optionally logs the CSAT as a HubSpot note.

## Setup

1. Add Jira HTTP Basic credentials (email + API token) and update the Jira base URL, project key, Done status name, label names, and custom field IDs in the embedded configuration code.
2. Configure the Jira webhook to POST to this workflow’s “jira-csat” webhook URL and include the shared token (query parameter or x-webhook-token header) matching the workflow configuration.
3. Connect a Gmail OAuth2 account for sending customer emails and set the sender account you want to use.
4. Provide WAHA (WhatsApp HTTP API) header-auth credentials and confirm your WAHA base URL and session ID are correct for sending WhatsApp messages.
5. If you use HubSpot logging, add a HubSpot private app token as header auth and ensure the Jira ticket contains the HubSpot contact ID custom field.
6. After importing the template, copy the CSAT Form Trigger webhook path into the “CSAT Form Path Config” node so generated form links point to the correct form endpoint.

## FAQ

**What platforms does this workflow integrate with?**  
It integrates with Jira, Gmail, WhatsApp (via WAHA API), and HubSpot.

**How does the workflow send CSAT requests to customers?**  
CSAT requests are sent via WhatsApp using the WAHA API or via Gmail email.

**Can the workflow log CSAT responses in HubSpot?**  
Yes, it can optionally log CSAT responses as notes in HubSpot if a contact ID is provided.

## Related n8n templates from Intuz

- [Generate unique GPT-4 tweets on a schedule, skip duplicates via Google Sheets, and post them to Twitter (X) automatically.](https://github.com/Intuz-production/Twitter-Post-Automation)
- [Turn confirmed Airtable sales orders into QuickBooks invoices — find or create the customer, generate the invoice, and write the Invoice ID back to Airtable.](https://github.com/Intuz-production/Airtable-to-QuickBooks-invoice-automation)
- [Get instant Slack alerts when QuickBooks invoices are created or updated — customer, amount, and due date in your team channel, in real time.](https://github.com/Intuz-production/QuickBooks-Slack-Automation)

[See all of Intuz's free n8n templates](https://www.intuz.com/n8n-workflow-automation-templates/)

## Connect with us

Intuz is a USA-based AI & workflow automation company with 16+ years of experience building custom AI-enabled workflow automations for SMBs and Enterprises, specializing in agentic AI, LLM integrations, and CRM/ERP sync across Healthcare, FinTech, eCommerce, Manufacturing, and Real Estate.

* **Website:** [https://www.intuz.com](https://www.intuz.com)
* **Email:** [getstarted@intuz.com](mailto:getstarted@intuz.com)
* **LinkedIn:** https://www.linkedin.com/company/intuz/
* **Get Started:** https://n8n.partnerlinks.io/intuz

## For Custom Workflow Automation

[Click here - Get Started](https://www.intuz.com/get-started/)
