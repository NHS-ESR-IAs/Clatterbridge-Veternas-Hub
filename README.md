# HM Forces Veterans Hub &mdash; Clatterbridge

A standalone web application and ESR signposting portlet providing information and resources to support NHS colleagues who are HM Forces Veterans, Reservists, Cadet Adult Volunteers, and Armed Forces family members.

---

## 📁 Repository Structure

```
.
├── index.html                      # Standalone Veterans & Armed Forces Hub website
├── launcher.html                   # ESR Signposting Portlet snippet (Pure HTML/CSS, No JS)
├── launcher.txt                    # Plain text copy of launcher.html
├── launcher-liferay.html           # ESR Liferay Dashboard boilerplate preview
├── launcher-liferay.txt            # Plain text copy of launcher-liferay.html
├── portlet.html                    # Original legacy ESR portlet (updated & preserved for reference)
├── Sources/                        # Source email requests and policy documents
│   ├── Armed Forces ESR page .eml
│   ├── Re- Armed Forces ESR page .eml
│   └── QP3636_Special Leave Policy.pdf
└── assets/                         # Local assets & award logos
    ├── Veterans.jpg                # Veterans banner & logo image
    ├── QP3636_Special Leave Policy.pdf # Special Leave Policy PDF
    ├── award_logo_1.png            # Award recognition logo 1
    └── award_logo_2.png            # Award recognition logo 2
```

---

## 🌐 1. Standalone Website (`index.html`)

Due to ESR's discontinuation of custom JavaScript execution in portal portlets, the full interactive hub lives as a standalone web application.

### Key Features:
- **Preserved NHS Styling**: Modern NHS color palette (`#005eb8`, `#0072c6`, `#41B6E6`, `#ffb81c`), responsive grid, and clean sidebar navigation.
- **Updated Content & Policies**:
  - **Special Leave Policy (QP3636 / HR04 v4.3)**: Replaces former reservist policy PDF while a dedicated Armed Forces policy is in development.
  - **Armed Forces Health Training (Module 1)**: Integrated regional VCHA trainer program information with direct access link.
  - **Armed Forces Staff Network**: Dedicated section with monthly meeting information and contact details for Network Chair Simon Glazebrook.
  - **Award Logos**: Displays the Trust's Armed Forces award recognition logos.
- **Deep-linking & History Support**:
  - `#Vet_LP` &mdash; Welcome & Overview
  - `#Vet_Status` &mdash; Recording Veteran Status in ESR
  - `#Vet_Policy` &mdash; Special Leave Policy
  - `#Vet_SCT` &mdash; Armed Forces Health Training (Module 1)
  - `#Vet_StaffNetwork` &mdash; Armed Forces Staff Network
  - `#Vet_AFC` &mdash; Armed Forces Covenant & Defence Employer Recognition Scheme (ERS)

---

## 📌 2. ESR Signposting Portlet (`launcher.html`)

Use the code in [`launcher.html`](launcher.html) when adding or updating a custom HTML portlet inside the ESR Dashboard.

### Deployment Instructions for ESR:
1. Open [`launcher.html`](launcher.html) or [`launcher.txt`](launcher.txt).
2. Copy the entire HTML/CSS snippet.
3. Paste directly into your ESR Custom Portlet box.

---

## ⚡ 3. Recording Veteran Status in ESR

To eliminate session errors and avoid cross-VPD authentication blocks, the Hub provides clear 4-step guidance directly to staff:
1. Log in to **My ESR** (`https://my.esr.nhs.uk/dashboard/`).
2. Navigate to **Personal Information** / My ESR.
3. Select the **Wellbeing** tab.
4. Complete the Armed Forces questions and submit.
