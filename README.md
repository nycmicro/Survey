# Nikon Ti2 with W1 SoRa Survey Website

This package contains a customer-facing survey webpage for the **Nikon Ti2 with W1 SoRa Demonstration at NYU Langone**.

## Included

- Branded landing page inspired by the attached SoRa flyer
- **Jump to Survey** buttons in the header and hero section
- Full survey form using the questions you provided
- Email notification to **Lauren.Richmond@nikon.com**
- Confirmation email to the person who submitted the form

## Files

- `public/index.html` — webpage markup
- `public/styles.css` — Nikon-inspired styling
- `public/script.js` — form submission logic
- `public/assets/hero.png` — hero image extracted from the flyer
- `public/assets/nikon-logo.png` — Nikon logo extracted from the flyer
- `server.js` — Express server + email sending endpoint
- `.env.example` — SMTP configuration template

## Setup

1. Install dependencies:
   ```bash
   npm install
   ```

2. Create your environment file:
   ```bash
   cp .env.example .env
   ```

3. Edit `.env` with your SMTP credentials.

   Example values:
   ```env
   PORT=3000
   RECIPIENT_EMAIL=Lauren.Richmond@nikon.com
   SMTP_HOST=smtp.yourprovider.com
   SMTP_PORT=587
   SMTP_SECURE=false
   SMTP_USER=your_username
   SMTP_PASS=your_password
   SMTP_FROM="Nikon SoRa Survey <no-reply@yourdomain.com>"
   ```

4. Start the site:
   ```bash
   npm start
   ```

5. Open:
   ```
   http://localhost:3000
   ```

## Notes

- The form will not send emails until valid SMTP credentials are added.
- The internal notification email is sent to `RECIPIENT_EMAIL`.
- The responder receives a confirmation email at the address they enter in the form.
- `replyTo` is set so Lauren can reply directly to the submitter.

## Deployment

You can deploy this on any Node.js-compatible host. After deployment, add the same environment variables there.

## Customization

You can easily edit:
- contact details in `public/index.html`
- survey copy in `public/index.html`
- email subject lines and templates in `server.js`
- styling in `public/styles.css`
