# Gmail Customer Support Automation

An automated Gmail workflow built using **n8n** that detects damaged-product complaints and sends an acknowledgement email automatically.

## Project Overview

Customer support teams receive repetitive emails every day. This workflow automates the initial response to customers reporting damaged products.

It monitors incoming Gmail messages, checks for the keyword `damaged`, and sends an acknowledgement when a match is found.

## Workflow Architecture

```text
Gmail Trigger
     |
     v
IF Node (Check for "damaged")
     |
     v
Set Node (Prepare Response)
     |
     v
Gmail Reply
```

## Technologies Used

- n8n: Workflow automation
- Gmail API: Email integration
- Google OAuth 2.0: Authentication

## How It Works

1. **Gmail Trigger:** Checks for incoming emails every minute.
2. **IF Node:** Checks whether the email snippet contains the keyword `damaged`.
3. **Set Node:** Prepares an automated customer acknowledgement.
4. **Gmail Reply:** Sends the response to the original email thread.

## Example

**Incoming Email:**

"My order arrived damaged. I would like a replacement. Please help me."

**Automated Response:**

"We're sorry your product arrived damaged. We understand the inconvenience. We've received your replacement request and our support team will assist you shortly."

## Setup Instructions

1. Install and open n8n.
2. Import `gmail-customer-support-workflow-sanitized.json`.
3. Configure your Gmail OAuth 2.0 credentials.
4. Connect the Gmail Trigger and Gmail Reply nodes to your account.
5. Test the workflow using a sample customer email.
6. Review the conditions and response before activating the workflow.

## Testing

The workflow was tested using a sample damaged-product complaint.

**Result:** The incoming email was detected, the condition matched, and an acknowledgement was successfully sent through Gmail.

## Current Limitations

- Uses keyword matching rather than AI-based intent detection.
- Only checks the email snippet for the word `damaged`.
- Does not verify order details or replacement eligibility.
- Sends a fixed acknowledgement rather than generating a personalized response.
- Requires further safeguards before production use.

## Future Improvements

- AI-based customer intent classification.
- Automatic extraction of order details.
- Integration with an order management system.
- Different responses for different complaint categories.
- Human approval for sensitive customer requests.

## Security

- OAuth credentials must be configured separately.
- Never upload client secrets, access tokens, or private customer emails.
- Review permissions before connecting a personal Gmail account.

## Author

**Rishand M.**

Built as a practical project while learning workflow automation and API integrations.
