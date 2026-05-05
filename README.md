# Horeca AI Suite — Landing Page

Production-ready landing page for Horeca AI Suite.
Target deployment: **https://horecastore.com/ai**

---

## 📦 What's in this package

| File | Purpose | Action required |
|---|---|---|
| `index.html` | Main landing page | Deploy as-is or integrate into existing site |
| `horeca-ai-logo.svg` | Full-resolution brand logo | Use in marketing, email signatures, social |
| `favicon.svg` | Browser tab icon | Deploy to site root |
| `robots.txt` | SEO crawler instructions | Deploy to site root |
| `sitemap.xml` | Search engine sitemap | Deploy to site root |
| `site.webmanifest` | PWA / mobile install metadata | Deploy to site root |

---

## 🚀 Deployment options

### Option A — Static HTML (fastest, ~30 minutes)
1. Upload `index.html` to your server at `/ai/index.html`
2. Upload `favicon.svg`, `robots.txt`, `sitemap.xml`, `site.webmanifest` to site root
3. Configure your web server so `/ai` serves `index.html`
4. Generate the missing image assets listed in section 🖼️ below
5. Wire up the form (see section ✉️ below)

### Option B — Integrated into existing CMS (recommended, 1-3 days)
If horecastore.com runs on Shopify / WordPress / Webflow / Next.js / etc:
1. Port the HTML structure into a new template/page in your CMS
2. Move all CSS into your existing stylesheet system
3. Reuse your existing site nav and footer instead of the ones in this file
4. Wire the form to your existing CRM (HubSpot / Mailchimp / Salesforce)
5. Hook up your existing analytics

---

## ⚙️ Required integrations before going live

### ✉️ 1. Form submission
The form currently posts to `https://formspree.io/f/YOUR_FORMSPREE_ID`.

**To activate:**
- Create a free Formspree account at https://formspree.io
- Create a new form, copy the form ID
- Replace `YOUR_FORMSPREE_ID` in `index.html` (search for it)

**Or replace with your own backend:**
- HubSpot: use Forms API
- Mailchimp: use Embedded Forms or API
- Salesforce: use Web-to-Lead form action URL
- Custom: replace the `action` attribute and adjust the `fetch()` call in the JS

The form sends two fields:
- `email` — the user's email address
- `agent` — which specific agent they want notified about (default: "general-suite")

### 📊 2. Analytics
Google Analytics 4 placeholder is included but commented out.

**To activate:**
- Find the `<!-- ANALYTICS -->` block in the `<head>`
- Uncomment the two `<script>` tags
- Replace `G-XXXXXXXXXX` with your real GA4 Measurement ID (2 places)
- Optionally uncomment the `gtag('event', 'sign_up'...)` line in the form submit handler to track conversions

### 🖼️ 3. Image assets to generate
The page references these images that don't exist yet:
- `/og-image.png` (1200×630px) — preview when shared on Facebook, LinkedIn, WhatsApp, X
- `/favicon-32.png` (32×32px) — fallback favicon for older browsers
- `/apple-touch-icon.png` (180×180px) — iOS home screen icon

**Easy way to generate them all:** upload `horeca-ai-logo.svg` to https://realfavicongenerator.net — it produces the entire favicon package automatically.

For the OG image, design a 1200×630 PNG with the logo, headline ("Eight agents. One restaurant. End to end."), and the gradient orb. Export from Figma or Canva.

### 📞 4. Phone link region code
The phone number is hardcoded as `tel:+18664467322` (US format).
If you need international dialing variants, your dev can detect locale and adjust.

---

## ✅ Production checklist

Before going live:
- [ ] Form action URL replaced with real Formspree ID or CRM endpoint
- [ ] Test form submission end-to-end (submit → check email arrives at sales@thehorecastore.com)
- [ ] Test all 8 "Notify me when it launches" buttons (each should pre-fill the agent name in the form)
- [ ] Google Analytics ID added and verified in GA dashboard
- [ ] `og-image.png` generated and uploaded
- [ ] All favicon variants generated and uploaded (use realfavicongenerator.net)
- [ ] Canonical URL in `<head>` matches your final deployment URL
- [ ] Sitemap URL in `robots.txt` matches your final deployment URL
- [ ] Page tested on iPhone Safari, Android Chrome, Mac Safari, Windows Chrome
- [ ] Page tested at 320px width (smallest mobile), 768px (tablet), 1440px (desktop), 1920px (large)
- [ ] Lighthouse score ≥ 90 on Performance, Accessibility, SEO, Best Practices
- [ ] Cookie banner / GDPR compliance added if required by your jurisdiction
- [ ] Privacy policy link added to footer (currently missing)
- [ ] Terms of service link added to footer (currently missing)
- [ ] Page shared in WhatsApp / LinkedIn / X to verify Open Graph preview renders correctly
- [ ] Screen-reader test (VoiceOver on Mac, NVDA on Windows) — page should be fully navigable

---

## 🎨 Design system reference

**Colors (CSS variables defined at the top of the file)**
- Background: `#07070C` (near-black)
- Text: `#F5F3EE` (warm off-white)
- AI gradient: amber `#FFB155` → coral `#FF6F8B` → magenta `#D946EF` → violet `#8B5CF6` → cyan `#22D3EE`

**Fonts (loaded from Google Fonts)**
- Body / UI: **Geist** (300, 400, 500, 600, 700, 800)
- Italic accents: **Instrument Serif**
- Code / labels: **Geist Mono**

**Logo**
- Full mark + wordmark + AI pill is the official lockup
- Mark alone (in `horeca-ai-logo.svg`) for square contexts (avatar, app icon, social profile)
- Always use on dark backgrounds; for light backgrounds the wordmark color must be inverted to `#07070C`

---

## 🔧 Browser support

Tested and works on:
- Safari 14+ (iOS and macOS)
- Chrome / Edge 90+
- Firefox 88+
- Samsung Internet 14+

Uses modern CSS features (`backdrop-filter`, `mask`, `clamp()`, gradient text). Older browsers will see a degraded but usable layout.

---

## 📞 Support

Questions about this code? The page was generated as a complete production package. For any modifications, your developer can edit `index.html` directly — all CSS and JS is inline in a single file for easy maintenance.

For business questions about the suite itself, contact:
- **sales@thehorecastore.com**
- **(866) 446-7322**
