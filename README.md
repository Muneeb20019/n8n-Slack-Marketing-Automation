# AI Slack Marketing Automation System

An automated reporting pipeline built in **n8n** that processes weekly marketing campaign data, generates a full performance report using AI, creates a formatted Google Doc, and delivers all notifications and alerts directly to **Slack**.

---

## Key Features

*   **Automated Data Processing**: Fetches and validates campaign data from Google Sheets every week.
*   **AI-Powered Analysis**: Uses the OpenAI API to generate a natural-language summary, and actionable recommendations.
*   **Automated Report Generation**: Converts the AI's Markdown output to HTML and uploads it to Google Drive, creating a perfectly formatted Google Doc.
*   **Slack-Centric Notifications**: Delivers a clean success summary with a link to the final report directly to a designated Slack channel.
*   **Robust Error Handling**: If the initial data source is invalid or empty, a separate path is triggered that sends a specific, diagnostic alert to a Slack channel for immediate attention.

---

## Tools & Technologies
*   **Automation Platform**: n8n
*   **Data Source**: Google Sheets API
*   **AI Engine**: OpenAI API (GPT-4 / GPT-3.5)
*   **Document Creation**: Google Drive API, Markdown, HTML
*   **Core Communication Hub**: Slack 
*   **Data Transformation**: JavaScript

---

## Workflow Overview

The system is orchestrated via a single, end-to-end n8n workflow.

![Workflow Diagram](PASTE_IMAGE_LINK_HERE)



---

## Setup

1.  **Import Workflow**: Import the `workflow.json` from this repository into your n8n instance.
2.  **Configure Credentials**: Add credentials for Google Sheets/Drive, OpenAI, and Slack within n8n.
3.  **Update Node Endpoints**:
    *   In the `Get row(s) in sheet` node, update the Sheet ID to point to your data source.
    *   In both `Send a message` nodes (for success and error), update the Slack channel to your desired destination.
4.  **Activate Workflow**: Turn the workflow on.
