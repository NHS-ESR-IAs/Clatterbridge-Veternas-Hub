# HM Forces Veterans Hub &mdash; Clatterbridge

A standalone web application and ESR signposting portlet providing information and resources to support NHS colleagues who are HM Forces Veterans, Reservists, and Cadet Adult Volunteers.

---

## 📁 Repository Structure

```
.
├── index.html                   # Standalone Veterans Hub website
├── launcher.html                # ESR Signposting Portlet snippet (Pure HTML/CSS, No JS)
├── portlet.html                 # Original legacy ESR portlet (preserved for reference)
├── assets/                      # Local assets (downloaded and uncoupled from CodePen)
│   ├── LUFT_Veterans.png        # Veterans banner & logo image
│   └── LUFT_Revservist_Policy.pdf # Armed Forces Reservist Policy PDF
└── Assets -> assets             # Case-insensitive compatibility symlink
```

---

## 🌐 1. Standalone Website (`index.html`)

Due to ESR's discontinuation of custom JavaScript execution in portal portlets, the full interactive hub now lives as a standalone web application.

### Key Features:
- **Preserved Look & Feel**: Faithful to the original NHS styling, colors (`#0072c6`, `#005eb8`, `#41B6E6`), and sidebar navigation layout.
- **Uncoupled from External CDNs**: Images and policy documents are loaded locally from `assets/`.
- **Integrated PDF Viewing**: Displays the Armed Forces Reservist Policy inline with a fallback download button.
- **Deep-linking & History Support**: Supports direct section navigation via URL hash:
  - `#Vet_LP` &mdash; Welcome & Overview
  - `#Vet_Status` &mdash; Recording Veteran Status in ESR
  - `#Vet_Policy` &mdash; Armed Forces Reservist Policy
  - `#Vet_SCT` &mdash; Service Champion Training
  - `#Vet_AFC` &mdash; Armed Forces Covenant & Defence Employer Recognition Scheme
- **Fully Responsive**: Adapts seamlessly to desktop and mobile screens.

---

## 📌 2. ESR Signposting Portlet (`launcher.html`)

Use the code in [`launcher.html`](launcher.html) when adding or updating a custom HTML portlet inside the ESR Dashboard.

### Why this is needed:
ESR portlets no longer allow JavaScript execution. `launcher.html` is built with **100% pure HTML and scoped inline CSS** without any JavaScript. It presents the standard NHS Veterans branding card and a button that opens the standalone website in a new tab.

### Deployment Instructions for ESR:
1. Host this project (e.g., via **GitHub Pages** under `https://nhs-esr-ias.github.io/Clatterbridge-Veterans-Hub/` or your Trust's internal web server).
2. Open [`launcher.html`](launcher.html).
3. Adjust the `href` in the launch button to point to your live site URL. You can append `?vpd=your-trust-slug` to automatically configure the link for your Trust (e.g. `?vpd=the-clatterbridge-cancer-centre-nhs-foundation-trust` or `?vpd=business-services-authority`).
4. Copy the entire HTML/CSS snippet from `launcher.html` and paste it into your ESR Custom Portlet.

---

## ⚡ 3. Dynamic Multi-VPD Support

The "Open ESR Personal Information Form" link dynamically resolves across any NHS Trust / VPD without modifying the source code:

1. **URL Parameter (`?vpd=...`)**:
   - Simply pass `index.html?vpd=<trust-slug>` (e.g., from `launcher.html` or an intranet bookmark).
2. **ESR Referrer Auto-Detection**:
   - If a user clicks into the site directly from their ESR dashboard, the hub parses the Trust slug from `document.referrer` automatically.
3. **Interactive On-Page Switcher**:
   - Users or administrators can click **"Switch Trust / VPD"** on the form page to select from quick presets (Clatterbridge, NHSBSA, LUFT, Sheffield) or enter a custom Trust slug. The selection is remembered in `localStorage`.
4. **Universal Fallback**:
   - If direct portlet actions are blocked by session rules, a direct link to the standard ESR Dashboard (`https://my.esr.nhs.uk/dashboard/`) is always available.

