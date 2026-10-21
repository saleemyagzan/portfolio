# Saleem Khan Portfolio — V2

## What changed
Premium visual refinements, scroll reveal effects, branded positioning ribbon, metadata, and a Cloudflare Pages Function for inquiry delivery. Existing audit and JSA demonstrations are preserved.

## Deploy
Upload this ZIP using Cloudflare Pages direct upload, preserving the `functions/api/contact.js` directory. Cloudflare Pages Functions deployment through dashboard drag-and-drop may NOT support Functions; use Git integration or Wrangler deployment for the backend. Static-only upload leaves the contact endpoint nonfunctional, and the form will report an error instead of pretending success.

## Activate real inquiries
1. Set up Resend and verify a sending domain (may require domain ownership; free-tier limits apply).
2. In Cloudflare Pages project Settings > Variables and Secrets, add encrypted `RESEND_API_KEY`, `CONTACT_TO_EMAIL` (your receiving address), and `CONTACT_FROM_EMAIL` (verified sender address, e.g. Portfolio <hello@yourdomain.com>).
3. Deploy Functions via Cloudflare Git integration or Wrangler CLI (not static ZIP-only drag and drop).
4. Submit a test inquiry, check receipt and Reply-To, and review Cloudflare logs.
5. Before publicly advertising the form, add abuse protection (Turnstile with client widget + server secret, and rate limits), privacy notice, and data handling policy. The server supports a TURNSTILE_SECRET check but the client widget has not been integrated yet: do not set that secret until the widget is added.

No API keys are bundled. No messages are stored by this website. The email provider processes message content for delivery. Do not use confidential or sensitive client information in the form.

## Local testing
Open `index.html` to preview visuals, audit, and JSA. Contact delivery only works after server deployment and configuration.
