# Big Mo's Luffas

A complete e-commerce storefront for Big Mo's Luffas — naturally grown luffas and branded merchandise, designed for Azure Static Web Apps.

## What's Included

- **Product Hub** (`index.html`) – Luffa products, benefits, and ordering
- **Merchandise Shop** (`shop.html`) – T-shirts and apparel with hilarious designs
- **404 Page** (`404.html`) – Branded error page
- **Security Headers** (`staticwebapp.config.json`) – Azure SWA configuration

## Features

✓ Fully responsive design (mobile, tablet, desktop)  
✓ Light/dark theme toggle with localStorage  
✓ Accessible WCAG AAA–compliant color scheme  
✓ No build step, no runtime dependencies  
✓ mailto: contact forms (no backend required)  
✓ Zero JavaScript frameworks  

## Local Development

### Quick Preview
``powershell
cd "C:\Users\morichar\OneDrive - Microsoft\Documents\Microsoft Scout\big-mos-luffas"
python -m http.server 4173
# Then open http://127.0.0.1:4173
``

## Azure Static Web Apps Deployment

### 1. Connect GitHub Repository
1. In [Azure Portal](https://portal.azure.com), create a new **Static Web App** resource
2. Select **GitHub** as the source, authenticate, and select the `MSPFE2019/big-mos-luffas` repository
3. Use these build settings:

| Setting | Value |
| --- | --- |
| **App location** | `/` |
| **API location** | *(blank)* |
| **Output location** | *(blank)* |

4. Click **Create** — Azure will create a GitHub Actions workflow automatically

### 2. Merchandise Integration (Printful, Stripe, etc.)

The `shop.html` page features 8 t-shirt designs. Currently, "Order" buttons trigger email confirmations. To connect live fulfillment:

**Option A: Printful**
- Create Printful account and product catalog
- Use Printful API for pricing/orders
- Replace onclick handlers with API calls

**Option B: Stripe + Serverless**
- Add serverless function for payment processing
- Connect Stripe for checkout
- Handle order fulfillment via email/webhook

### 3. Custom Domain

After deployment, add a custom domain via Azure Portal:  
**Settings** → **Custom domains** → Add your domain → Follow DNS setup

## Project Structure
``
big-mos-luffas/
├── index.html                # Luffa product hub
├── shop.html                 # T-shirt merchandise
├── 404.html                  # Error page
├── staticwebapp.config.json  # Azure SWA config
├── .gitignore
└── README.md
``

## Security

Built-in headers in `staticwebapp.config.json`:
- Content-Security-Policy (CSP)
- X-Frame-Options: DENY
- X-Content-Type-Options: nosniff
- Referrer-Policy: strict-origin-when-cross-origin

## Customization

**Colors:** Edit CSS variables in the `<style>` block  
**Content:** Update HTML directly in index.html and shop.html  
**Email:** Replace `hello@bigmosluffas.com` in form submissions  

## Support

Repository: `MSPFE2019/big-mos-luffas`

---

Hosted on **Azure Static Web Apps** — free hosting with automatic CI/CD from GitHub.
