# HM Forces Veterans Hub &mdash; Clatterbridge

A standalone web application and ESR signposting portlet providing information and resources to support NHS colleagues who are HM Forces Veterans, Reservists, and Cadet Adult Volunteers.

---

## 📁 Repository Structure

```
.
├── index.html                   # Standalone Veterans Hub website
├── launcher.html                # ESR Signposting Portlet snippet (Pure HTML/CSS, No JS)
├── launcher-liferay.html        # ESR Liferay Dashboard boilerplate preview
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
1. Host this project (e.g., via **GitHub Pages** under `https://nhs-esr-ias.github.io/Clatterbridge-Veternas-Hub/` or your Trust's internal web server).
2. Open [`launcher.html`](launcher.html).
3. The links are pre-configured to point to `https://nhs-esr-ias.github.io/Clatterbridge-Veternas-Hub/`.
4. Copy the entire HTML/CSS snippet from `launcher.html` and paste it into your ESR Custom Portlet.

---

## ⚡ 3. Recording Veteran Status in ESR

To eliminate session errors and avoid cross-VPD authentication blocks, the Hub provides clear 4-step guidance directly to staff:
1. Log in to **My ESR** (`https://my.esr.nhs.uk/dashboard/`).
2. Navigate to **Personal Information** / My ESR.
3. Select the **Wellbeing** tab.
4. Complete the Armed Forces questions and submit.

The action button links directly to `https://my.esr.nhs.uk/dashboard/` so users from any Trust can log in without encountering expired CSRF tokens or permissions issues.

