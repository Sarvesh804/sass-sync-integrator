# SaaS Sync Integrator

This is a MuleSoft-based integration flow that simulates syncing customer data from a mock CRM (like Salesforce) to a custom Order Management system.

## Project Overview

This project demonstrates a real-world enterprise integration use case:

- Fetch data from a CRM system (simulated using Postman mock server)
- Transform the data into a target schema using DataWeave
- Push the transformed data to an order management endpoint
- Automatically schedule the flow to run periodically
- Handle errors gracefully using try-catch scopes and log relevant issues

## Technologies Used

- MuleSoft Anypoint Studio (Runtime 4.4.x)
- DataWeave 2.0
- HTTP connectors
- Postman (for mock API)
- Webhook.site (for simulating order API)
- Git for version control

## Flow Design

There are two flows:

### 1. Manual Trigger Flow

- Triggered via HTTP GET request at `/sync`
- Fetches customer data from mock CRM
- Transforms the data
- Sends it to a test endpoint (Webhook.site)
- Logs the data and handles errors

### 2. Scheduled Flow

- Runs automatically every 1 minute (configurable)
- Executes the same data sync logic
- Demonstrates scheduling, retry logic, and logging

## How to Run

1. Open the project in Anypoint Studio
2. Right-click the project → Run As → Mule Application
3. Use a browser or Postman to trigger:

```bash
GET http://localhost:8081/sync
```

4. Check the webhook endpoint for incoming data
5. To test the scheduler, wait for 1-minute intervals


