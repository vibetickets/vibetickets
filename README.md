<div align="center">

<img src="https://hievents-public.s3.us-west-1.amazonaws.com/website/github-banner.png?v=1" alt="VibeTickets - Cloudflare Workers Distribution of Hi.Events" width="100%">

# VibeTickets

### Cloudflare Workers distribution of Hi.Events

Sell tickets online for conferences, nightlife events, concerts, club nights, workshops, and festivals.  
Self-hosted backend with Cloudflare Workers frontend. Your events, your brand, your data.

[Live Demo](https://tickets.vibetickets.tech) · [Documentation](https://hi.events/docs) · [Upstream Project](https://github.com/HiEventsDev/hi.events)

[![License: AGPL v3](https://img.shields.io/badge/License-AGPL_v3-blue.svg)](https://github.com/vibetickets/vibetickets/blob/develop/LICENCE)
[![GitHub Release](https://img.shields.io/github/v/release/vibetickets/vibetickets?include_prereleases)](https://github.com/vibetickets/vibetickets/releases)
[![Fork Status](https://img.shields.io/badge/Fork-Hi.Events-success)](https://github.com/HiEventsDev/hi.events)
[![Cloudflare Workers](https://img.shields.io/badge/Frontend-Cloudflare%20Workers-orange)](https://workers.cloudflare.com/)

</div>

<br>

## Why VibeTickets?

Most ticketing platforms charge per-ticket fees and lock your data into their ecosystem. **Hi.Events is a modern,
open-source alternative to Eventbrite, Tickettailor, Dice.fm, and other ticketing platforms** for organizers who want
full control over branding, checkout, data, and infrastructure.

**VibeTickets** is a community distribution of Hi.Events optimized for **Cloudflare Workers** frontend deployment. We maintain full compatibility with upstream Hi.Events while adding edge deployment capabilities. All improvements to core functionality are contributed back to the original project.

Built for nightlife promoters, festival organizers, venues, community groups, and conference hosts.

<br>

<img alt="Hi.Events Dashboard" src="https://hievents-public.s3.us-west-1.amazonaws.com/website/github-screenshot.png"/>

<br>

## Features

<table>
<tr>
<td width="50%" valign="top">

### 🎟️ Ticketing & Sales

- Flexible ticket types (free, paid, donation, tiered)
- Hidden and locked tickets behind promo codes
- Promo codes and pre-sale access
- Product add-ons (merch, upgrades, extras)
- Product categories for organization
- Full tax and fee support (VAT, service fees)
- Capacity management and shared limits

</td>
<td width="50%" valign="top">

### 🎨 Branding & Customization

- Beautiful, conversion-optimized checkout
- Customizable PDF ticket designs
- Branded organizer homepage
- Drag-and-drop event page builder
- Embeddable ticket widget
- SEO tools (meta tags, Open Graph)

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 👥 Attendee Management

- Custom checkout questions
- Advanced search, filtering, and export (CSV/XLSX)
- Full and partial refunds
- Bulk messaging by ticket type
- QR code check-in with scan logs
- Access-controlled check-in lists

</td>
<td width="50%" valign="top">

### 📊 Analytics & Growth

- Real-time sales dashboard
- Affiliate and referral tracking
- Advanced reporting (sales, tax, promos)
- Webhooks (Zapier, Make, CRMs)

</td>
</tr>
<tr>
<td colspan="2" valign="top">

### ⚙️ Operations

Multi-user roles and permissions · Stripe Connect instant payouts · Offline payment methods · Offline event support ·
Automatic invoicing · Event archive · Multi-language support · Full REST API

</td>
</tr>
</table>

<br>

## Compare

| Feature                          | Hi.Events | Eventbrite | Tickettailor | Dice    |
|:---------------------------------|:----------|:-----------|:-------------|:--------|
| Self-hosted option               | ✅         | ❌          | ❌            | ❌       |
| Open source                      | ✅         | ❌          | ❌            | ❌       |
| No per-ticket fees (self-hosted) | ✅         | ❌          | ❌            | ❌       |
| Full custom branding             | ✅         | Limited    | ✅            | Limited |
| Affiliate tracking               | ✅         | ✅          | ❌            | ❌       |
| API access                       | ✅         | ✅          | ✅            | Limited |
| Own your data                    | ✅         | ❌          | ❌            | ❌       |

<br>

## Quick Start

### Cloudflare Workers (Frontend)

Deploy the frontend to Cloudflare Workers for edge caching:

```bash
git clone git@github.com:vibetickets/vibetickets.git
cd vibetickets/frontend

# Install dependencies
npm install

# Configure environment
cp .env.example .env
# Edit: VITE_API_URL_CLIENT, VITE_API_URL_SERVER, VITE_FRONTEND_URL, VITE_STRIPE_PUBLISHABLE_KEY
# Optional: VITE_APP_PRIMARY_COLOR, VITE_APP_SECONDARY_COLOR

# Build and deploy
npm run build:worker
npx wrangler deploy
```

### Docker (Backend)

```bash
git clone git@github.com:vibetickets/vibetickets.git
cd vibetickets/docker/backend

# Generate keys (Linux/macOS)
echo "APP_KEY=base64:$(openssl rand -base64 32)" >> .env
echo "JWT_SECRET=$(openssl rand -base64 32)" >> .env

docker compose up -d
```

Open `http://localhost:8123` and create your account.

📖 [Full installation guide](https://hi.events/docs/getting-started)

<br>

## Branding Assets

To customize the frontend with your own branding, replace the following assets in `frontend/public/` while keeping the original filenames:

### Logo Files
```
logos/
├── hi-events-horizontal-dark.svg
├── hi-events-horizontal-light.svg
├── hi-events-icon-dark.svg
├── hi-events-icon-light.svg
├── hi-events-logo-preview.html
├── hi-events-stacked-dark.svg
├── hi-events-stacked-light.png
├── hi-events-stacked-light.svg
├── hi-events-text-dark.svg
└── hi-events-text-light.svg
```

### Favicon and Icons
```
manifest-icons/
├── apple-touch-icon.png
├── favicon-16x16.png
├── favicon-192x192.png
├── favicon-32x32.png
├── favicon-48x48.png
├── favicon-512x512.png
├── favicon.ico
├── favicon-light-48x48.png
├── favicon-light.svg
├── favicon.svg
└── favicon-text-dot.svg
favicon.ico
```

### Environment Variables
Add your brand colors to the frontend `.env`:
```env
VITE_APP_PRIMARY_COLOR="#c9ff1f"
VITE_APP_SECONDARY_COLOR="#B61FFF"
```

<br>

## Contributing

We are active contributors to Hi.Events. This fork maintains a pristine `upstream-develop` branch for contributing back to the original project.

To contribute to Hi.Events:
1. Branch from `upstream-develop` (tracks Hi.Events/develop)
2. Follow [Hi.Events Contributing Guidelines](https://github.com/HiEventsDev/hi.events/blob/develop/CONTRIBUTING.md)
3. Sign the CLA: `I have read the CLA Document and I hereby sign the CLA`
4. PR to `HiEventsDev/hi.events:develop`

For VibeTickets-specific issues (Cloudflare Workers deployment):
1. Branch from `develop`
2. Submit PR to this repository

<br>

## Support

📖 [Documentation](https://hi.events/docs) · 📧 [hello@hi.events](mailto:hello@hi.events) ·
🐛 [GitHub Issues](https://github.com/vibetickets/vibetickets/issues)

<br>

## Changelog

Stay updated with new features and improvements on
the [releases page](https://github.com/vibetickets/vibetickets/releases).

<br>

## License

VibeTickets is a derivative work of [Hi.Events](https://github.com/HiEventsDev/hi.events), licensed under **AGPL-3.0**.

[View Full License](https://github.com/vibetickets/vibetickets/blob/develop/LICENCE)

<br>

<div align="center">

**[Website](https://hi.events)** · **[Documentation](https://hi.events/docs)** · **[Upstream Project](https://github.com/HiEventsDev/hi.events)**

Made with ☘️ in Ireland · Deployed on the Edge

</div>
