# AI Slack Marketing Automation System

An automated reporting pipeline built in **n8n** that processes weekly marketing campaign data, generates a full performance report using AI, creates a formatted Google Doc, and delivers all notifications and alerts directly to **Slack**.

---

## Key Features

*   **Automated Data Pipeline:** Triggers weekly to fetch and validate raw campaign data from **Google Sheets**, with a data quality gate to ensure reliability.

*   **AI-Powered Content Generation:** An **OpenAI** agent generates the **entire report content**—including a full data table, summary, and recommendations—in a single, structured Markdown block.

*   **High-Fidelity Document Creation:** The Markdown is converted to HTML and then uploaded to **Google Drive**, which automatically converts it into a perfectly formatted Google Doc with all styles and tables intact.

*   **Dual-Channel Slack Notifications:**
    *   **Success:** A clean summary and a link to the report are sent to a public channel.
    *   **Failure:** A separate error-handling path sends a diagnostic alert to an internal channel if the initial data source is invalid, ensuring robust monitoring.

*   **Robust Architecture:** The workflow uses custom **JavaScript** for data transformation and is designed with clear, commented sections and robust error handling, making it both powerful and maintainable.

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

![Workflow Diagram](https://github.com/Muneeb20019/n8n-Slack-Marketing-Automation/blob/main/n8n-slack%20workflow.png?raw=true)
---

## Setup

1.  **Import Workflow**: Import the `workflow.json` from this repository into your n8n instance.
2.  **Configure Credentials**: Add credentials for Google Sheets/Drive, OpenAI, and Slack within n8n.
3.  **Update Node Endpoints**:
    *   In the `Get row(s) in sheet` node, update the Sheet ID to point to your data source.
    *   In both `Send a message` nodes (for success and error), update the Slack channel to your desired destination.
4.  **Activate Workflow**: Turn the workflow on.

   ---
## Author

- [Muneeb Ali Khan] (https://www.linkedin.com/in/muneeb-ali-khan-2a1675365)
