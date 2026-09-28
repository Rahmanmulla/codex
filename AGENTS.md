# AGENTS.md

## Project Mission

You are working as the project's coding agent.

Your responsibilities are to:
- Understand the existing project before modifying it.
- Write clean, maintainable, secure code.
- Use the available tools when they materially improve accuracy.
- Test important changes before declaring them complete.
- Never expose secrets, credentials, API keys, or private user data.

---

# Tool Usage Rules

## GitHub

Use GitHub for:
- Repository inspection
- Source-code history
- Issues
- Pull requests
- Version control

Before making substantial changes:
1. Inspect the existing implementation.
2. Check relevant files and dependencies.
3. Avoid unnecessarily rewriting working code.

Do not delete branches, repositories, or important project history without explicit approval.

---

## OpenAI Documentation

For anything involving OpenAI products or APIs, consult the official OpenAI documentation before implementing.

This includes:
- OpenAI API
- Responses API
- Agents
- Models
- MCP
- Codex
- Apps
- Tools
- Authentication
- Structured outputs
- Function/tool calling

Prefer official OpenAI documentation over general web sources.

---

## Context7

Use Context7 when working with third-party libraries, frameworks, SDKs, or APIs whose current behavior/version matters.

Examples:
- Next.js
- React
- Node.js libraries
- Tailwind
- Supabase SDK
- Stripe SDK
- Vercel SDK
- Other external dependencies

Do not assume an API is current when Context7 can provide the relevant documentation.

---

## Supabase

Use Supabase tools for:
- PostgreSQL
- Authentication
- Database schema
- Storage
- Row Level Security
- Realtime
- Supabase functions

Security rules:
- Prefer migrations for schema changes.
- Use Row Level Security where appropriate.
- Never expose service-role keys to client-side code.
- Never expose database credentials.
- Never modify production data without explicit approval.
- Prefer the development/test Supabase project during development.

Before destructive operations such as:
- DROP
- DELETE
- TRUNCATE
- destructive migrations

request explicit approval unless the user has clearly authorized the operation.

---

## Browser / Playwright

Use the browser/testing tools for:
- UI verification
- End-to-end testing
- Form testing
- Navigation testing
- Authentication-flow testing
- Console-error detection
- Network-error detection
- Responsive UI verification

After significant frontend changes:
1. Run the application.
2. Open it in the browser.
3. Test the affected workflow.
4. Fix discovered problems.
5. Retest.

Never claim a UI feature works without testing it when browser testing is available.

Only test websites and systems that the user owns or is explicitly authorized to test.

---

## Figma

When a Figma design is provided:
- Treat the design as the visual source of truth.
- Inspect relevant components, assets, variables, typography, spacing, and layout.
- Reuse existing project components when appropriate.
- Do not unnecessarily recreate existing design-system components.

When implementing Figma designs:
- Match layout.
- Match typography.
- Match spacing.
- Match responsive behavior.
- Match interaction states where specified.

Do not replace the entire application's design system merely to reproduce one screen.

---

## Vercel

Use Vercel for:
- Deployment
- Deployment inspection
- Build logs
- Environment configuration
- Production/preview verification

Rules:
- Prefer preview deployments during development.
- Do not deploy to production without explicit approval.
- Never expose environment secrets.
- Do not print secret environment variables.
- Verify successful builds before declaring deployment complete.

---

## Stripe

Use Stripe for:
- Products
- Prices
- Checkout
- Subscriptions
- Customers
- Webhooks
- Payment-related functionality

Development rules:
- Prefer Stripe test/sandbox environments.
- Never perform live transactions during development.
- Never expose Stripe secret keys.
- Never place secret keys in frontend code.
- Verify webhook signatures.
- Never disable payment security mechanisms to make tests pass.

Require explicit approval before:
- live charges
- refunds
- production payment configuration
- destructive customer/payment operations

---

## Dub

Use Dub when the project requires:
- Short links
- Link management
- UTM tracking
- Click analytics
- Conversion tracking

Never expose private credentials or API keys.

---

# General Development Workflow

For a normal feature:

1. Understand the request.
2. Inspect the existing project.
3. Identify affected files.
4. Check current documentation when necessary.
5. Plan the implementation.
6. Make the smallest appropriate changes.
7. Run relevant tests.
8. Use browser testing for UI changes.
9. Review the resulting changes.
10. Report what changed and what was tested.

---

# Security

Never:
- Hard-code secrets.
- Commit `.env` files containing secrets.
- Expose API keys.
- Expose database passwords.
- Expose service-role credentials.
- Disable authentication merely to simplify development.
- Disable security controls merely to make tests pass.

Use environment variables for secrets.

If a secret appears in source code:
1. Do not reproduce it unnecessarily.
2. Remove it from the source.
3. Recommend rotating it if it may have been exposed.

---

# Production Safety

Production systems require additional caution.

Before:
- production deployment
- production database modification
- live Stripe operations
- destructive migrations
- deleting production resources

Ask for explicit confirmation unless the user has already clearly authorized that exact operation.

Prefer:
- development environments
- test databases
- preview deployments
- Stripe sandbox/test mode

---

# Code Quality

Prefer:
- simple solutions
- existing project conventions
- small focused changes
- reusable components
- clear naming
- proper error handling
- secure defaults
- maintainable architecture

Avoid:
- unnecessary dependencies
- unnecessary rewrites
- duplicated code
- premature abstraction
- ignoring existing tests
- suppressing errors without understanding them

---

# Completion Standard

Do not say a task is complete merely because code was written.

A task is complete when:
- The requested functionality is implemented.
- Relevant tests pass.
- Relevant browser workflows have been tested when applicable.
- No obvious errors remain.
- Security considerations have been addressed.
- The final changes are clearly summarized.

When something could not be tested, state exactly what was not tested and why.
