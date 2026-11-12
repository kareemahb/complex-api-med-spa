# GlowCheck ✨ Med Spa Medication Reference
 
A spa-inspired reference tool for med spa staff. Search a medication and see its **official FDA label details** next to a **plain-language background summary**, all in one place.
 
Built with plain HTML, CSS, and JavaScript for the **Complex API 2: Med Spa** challenge. Data from one API is used to make the request to a second API.
 
🔗 **Live Demo:** [kareemahb.github.io/complex-api-med-spa](https://kareemahb.github.io/complex-api-med-spa/)
 
<img width="1232" height="962" alt="GlowCheck search screen with FDA information and background cards" src="https://github.com/user-attachments/assets/97bc17a9-2f72-4f5f-a599-b33b48e2059a" />

 
## 🔍 How It Works
 
GlowCheck chains two free public APIs. Neither one needs an API key.
 
1. **[openFDA Drug Label API](https://open.fda.gov/apis/drug/label/)**: The user searches a brand or generic name, such as _Latisse_. The app checks `brand_name`, then `generic_name`, then `substance_name`. It returns the product's generic name, route, product type, and manufacturer.
2. **[Wikipedia REST API](https://en.wikipedia.org/api/rest_v1/)**: The app sends the **generic name returned by the FDA**, such as _Bimatoprost_, to Wikipedia's page summary endpoint. The summary tells staff what the medication is and how it's used.
```
User search ──▶ openFDA ──▶ generic name ──▶ Wikipedia ──▶ background summary
```
 
<img width="1232" height="969" alt="GlowCheck results for Latisse showing the FDA card and the Wikipedia background card" src="https://github.com/user-attachments/assets/9a467267-d8f2-45f8-9b17-3a26ad205198" />

 
## 🌿 Features
 
- **Two-API lookup**: the FDA response feeds straight into the Wikipedia request
- **Smart fallbacks**: searches brand, then generic, then substance name. Multi-word names are searched as exact phrases.
- **Title clean-up for Wikipedia**: FDA names come back in ALL CAPS, so the app tries cleaned-up title variations and skips disambiguation pages
- **Graceful errors**: if Wikipedia has no matching article, the FDA results still display
- **Quick-pick chips** for common med spa products: Botox, Dysport, Lidocaine, Tretinoin, Latisse
- **Search on Enter**, a loading state on the button, and friendly error messages
- **Responsive design** that stacks cleanly on mobile
- **Accessible markup**: a labeled input and an `aria-live` status message

 
## 🛠️ Tech Stack
 
- HTML5
- CSS3 (custom properties, Google Fonts: Cormorant Garamond and Jost)
- JavaScript (ES6+ class, `async`/`await`, Fetch API)
No frameworks, dependencies, or build tools.
 

 
## 📁 Project Structure
 
```
complex-api-med-spa/
├── index.html   # Page layout: search, quick picks, result cards
├── main.css     # Spa color palette, typography, responsive layout
└── main.js      # MedSpaApp class: events, API calls, rendering
```
 
---
 
## 🚀 Getting Started
 
Try it live on **[GitHub Pages](https://kareemahb.github.io/complex-api-med-spa/)**, or run it locally:
 
```bash
git clone https://github.com/kareemahb/complex-api-med-spa.git
cd complex-api-med-spa
```
 
Open `index.html` in your browser, or use the **Live Server** extension in VS Code.
 

 
## 💡 What I Learned
 
- Chaining API calls so one request's response becomes the input for the next
- Writing fallback logic for when one API's data doesn't match another API's format
- Organizing a front-end app in a single class that holds DOM references, event listeners, and API calls
- Handling partial failures so one missing data source doesn't break the whole page

 
## ⚠️ Disclaimer
 
GlowCheck is for informational and educational purposes only. It is not medical advice.

 
## 👩‍💻 Created By
 
**Kareemah Bahaadur**
[GitHub @kareemahb](https://github.com/kareemahb)
