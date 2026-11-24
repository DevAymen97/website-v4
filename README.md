# LocationMaroc — Car Rental Website Template

A complete, bilingual (French/English) car rental website for a Moroccan agency.
Designed for GitHub Pages deployment — no backend required.

---

## 📁 File Structure

```
car-rental/
│
├── index.html              ← Homepage (Accueil)
├── parc.html               ← Fleet page (Parc Automobile)
├── about.html              ← About page (À Propos)
├── contact.html            ← Contact page
│
├── cars/                   ← Individual car detail pages
│   ├── dacia-sandero.html
│   ├── renault-clio.html
│   ├── volkswagen-polo.html
│   ├── hyundai-i20.html
│   ├── duster-4x4.html
│   ├── toyota-rav4.html
│   ├── mercedes-classe-c.html
│   └── bmw-serie5.html
│
├── css/
│   └── style.css           ← All styles
│
├── js/
│   ├── components.js       ← Navbar, Footer, WhatsApp injection + i18n data
│   └── main.js             ← All JavaScript (lang toggle, scroll, gallery, etc.)
│
└── images/                 ← (optional) Place local images here
    └── cars/
```

---

## 🚀 Deploy to GitHub Pages

1. Create a new GitHub repository (e.g., `locationmaroc`)
2. Upload all files maintaining the folder structure
3. Go to Settings → Pages → Source: `main` branch / root folder
4. Your site will be live at: `https://yourusername.github.io/locationmaroc/`

---

## 📱 WhatsApp Configuration

Edit `js/components.js` — find this line at the top and replace with your number:

```javascript
const WA_NUMBER = '212600000000'; // Replace with your real WhatsApp number
// Format: country code + number, no + or spaces
// Morocco example: 212661234567
```

---

## ➕ Adding a New Car

### Step 1 — Copy a car detail page
```bash
cp cars/dacia-sandero.html cars/your-car-name.html
```

### Step 2 — Edit the new file
- Replace all instances of "Dacia Sandero" with the car name
- Update the price (250 MAD → your price)
- Update specs (fuel, transmission, seats, power, etc.)
- Update the image URLs (use Unsplash or local paths)
- Update the WhatsApp pre-filled message (the `data-wa-car` attribute)

### Step 3 — Add card to parc.html
Copy one of the `<article class="car-card">` blocks and update the details.

### Step 4 — Add card to index.html (optional)
Same as Step 3, for the featured section on the homepage.

---

## 🌍 Language System

Languages are managed in `js/main.js` in the `translations` object.
Each key exists in both `fr` and `en` objects.

To add a new string:
1. Add it to both `fr` and `en` in the `translations` object
2. Use `data-i18n="your_key"` on any HTML element

For HTML content (with tags like `<em>`), also add `data-i18n-html="true"`.

---

## 🎨 Design Customization

All design tokens are CSS variables in `css/style.css`:

```css
:root {
  --accent:      #c8a96e;   /* Gold accent color */
  --accent-dark: #a8893e;   /* Darker gold on hover */
  --black:       #0a0a0a;   /* Main dark */
  --white:       #f8f6f2;   /* Off-white background */
  --cream:       #f2ede6;   /* Section backgrounds */
  --whatsapp:    #25D366;   /* WhatsApp green */
}
```

---

## ✅ Checklist Before Going Live

- [ ] Replace `212600000000` with real WhatsApp number in `js/components.js`
- [ ] Update address in `contact.html` and `js/components.js` footer
- [ ] Update email in `contact.html` and footer
- [ ] Replace Unsplash images with real car photos
- [ ] Update Google Maps embed URL in `contact.html`
- [ ] Update car prices and specs to match your real fleet
- [ ] Test on mobile (iPhone + Android)
- [ ] Test WhatsApp links (click opens WhatsApp with pre-filled message)
- [ ] Test FR/EN toggle on all pages
