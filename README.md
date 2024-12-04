# PearlThought-Assignment
Resilient email sending service in TypeScript/JavaScript.
# Resilient Email Sending Service

This project implements a robust email-sending service with the following features:
- Retry logic with exponential backoff
- Fallback between multiple providers
- Idempotency to prevent duplicate sends
- Rate limiting to control email sending rate
- Circuit breaker to avoid repeated failures

## Setup

1. Clone the repository.
2. Install dependencies: `npm install`
3. Run tests: `npm test`

## Usage

```typescript
import { EmailService } from "./src/EmailService";
import { MockEmailProvider } from "./src/MockEmailProvider";

const providers = [new MockEmailProvider("Provider1"), new MockEmailProvider("Provider2")];
const service = new EmailService(providers);

service.sendEmail(
  { to: "recipient@example.com", subject: "Hello", body: "This is a test email." },
  "unique-id"
);

