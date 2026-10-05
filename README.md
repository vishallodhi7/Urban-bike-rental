# Urban Rentals — Professional Two-Wheeler Rental Website

A fast, modern, and production-ready bike and scooter rental web platform for **Urban Rentals** (Delhi NCR).

Built with **React, TypeScript, Vite, and clean modular CSS**.

---

## ⚡ Quick Start

### 1. Prerequisites
- **Node.js**: v18.0.0 or higher
- **npm**: v9.0.0 or higher

### 2. Installation
Open a terminal in the project directory and run:

```bash
npm install
```

### 3. Run Development Server
Start the local development server at `http://localhost:3000`:

```bash
npm run dev
```

### 4. Build for Production
Create an optimized production bundle in the `dist/` folder:

```bash
npm run build
```

### 5. Preview Production Build
Preview the generated production build locally:

```bash
npm run preview
```

---

## 📁 Project Structure

```text
urban-rentals/
│
├── public/
│   ├── favicon.svg             # Website favicon
│   └── images/
│       └── bikes/              # Vehicle photography & illustrations
│
├── src/
│   ├── config/
│   │   └── business.ts         # ⭐️ Central business info (Phone, WhatsApp, Maps URL, Hours)
│   │
│   ├── data/
│   │   ├── bikes.ts            # ⭐️ Bike inventory (Models, Specs, Pricing, Features)
│   │   └── faqs.ts             # ⭐️ Frequently Asked Questions dataset
│   │
│   ├── components/
│   │   ├── Navbar.tsx          # Sticky navigation & mobile menu drawer
│   │   ├── Footer.tsx          # 4-column footer with contact and legal links
│   │   ├── BikeCard.tsx        # Reusable vehicle card
│   │   ├── QuickBookingSearch.tsx # Hero search & date picker card
│   │   ├── BookingForm.tsx     # 3-step rental request wizard & confirmation
│   │   ├── FAQAccordion.tsx    # Accessible interactive FAQ accordion
│   │   ├── MobileActionBar.tsx # Sticky bottom bar for mobile screens (Call | WhatsApp | Book)
│   │   └── SEO.tsx             # Page title & meta description manager
│   │
│   ├── pages/
│   │   ├── Home.tsx            # Hero, quick search, featured bikes, why us, how it works, location
│   │   ├── Bikes.tsx           # Full catalog with category, engine, price & search filters
│   │   ├── BikeDetails.tsx     # Vehicle details page with gallery, specs & booking card
│   │   ├── HowItWorks.tsx      # 4-step workflow, required documents, rental lifecycle
│   │   ├── About.tsx           # Company story, Nehru Vihar Delhi presence, values
│   │   ├── Contact.tsx         # Contact info cards, Google Maps embed, inquiry form
│   │   ├── FAQPage.tsx         # Full categorized FAQ directory
│   │   ├── Terms.tsx           # Rental terms & conditions with labeled [EDIT: ...] markers
│   │   └── Privacy.tsx         # Customer privacy policy
│   │
│   ├── styles/
│   │   ├── variables.css       # ⭐️ Theme colors (#0B0D0F dark base, #E8A317 gold accent)
│   │   └── global.css          # Global CSS reset, typography, buttons, and layout
│   │
│   ├── utils/
│   │   └── whatsapp.ts         # WhatsApp pre-filled message generator
│   │
│   ├── App.tsx                 # React Router routing & scroll restoration
│   └── main.tsx                # Entry point
│
├── package.json
├── tsconfig.json
└── vite.config.ts
```

---

## 🛠️ How to Customize the Website (Non-Developer Guide)

### 1. Where to Change Business Information, Phone, WhatsApp & Maps
All business details are centralized in **one single file**:
👉 `src/config/business.ts`

Open this file to update:
- **Business Name**: `name`
- **Phone Number**: `contact.phone` and `contact.phoneDisplay`
- **WhatsApp Number**: `contact.whatsapp` and `contact.whatsappDisplay`
- **Email Address**: `contact.email` and `contact.emailDisplay`
- **Physical Address**: `location.fullAddress`
- **Google Maps Link**: `links.googleMapsUrl` and `links.googleMapsEmbedUrl`
- **Opening Hours**: `operatingHours.hours`

*Changing values in this single file updates the entire website automatically!*

---

### 2. Where to Add, Edit, or Remove Bikes & Scooters
All vehicle data lives inside:
👉 `src/data/bikes.ts`

To add a new vehicle, simply add a new object to the `bikes` array:

```ts
{
  id: "tvs-jupiter-125",
  brand: "TVS",
  model: "Jupiter 125",
  fullName: "TVS Jupiter 125",
  category: "scooter", // 'scooter' | 'commuter' | 'sports' | 'cruiser' | 'premium'
  categoryLabel: "Scooter",
  engineCc: 125,
  engine: "124.8cc ET-Fi",
  transmission: "Automatic",
  fuel: "Petrol",
  mileage: "50 km/l",
  seats: 2,
  modelYear: "2024",
  pricePerDay: 549,
  priceFormatted: "₹549/day",
  securityDeposit: "₹1,500",
  available: true,
  image: "/images/bikes/activa-6g.svg",
  tagline: "Spacious and fuel-efficient scooter with all-day comfort.",
  description: "Great for city commuting, errands, and college transit in Delhi.",
  features: [
    "1 Helmet Included",
    "Pre-ride Inspection Completed",
    "Front Disc Brake"
  ],
  specs: {
    fuelTankCapacity: "5.1 Litres",
    kerbWeight: "108 kg",
    brakes: "Sync Braking Technology",
    startType: "Self / Kick Start"
  },
  isFeatured: true
}
```

---

### 3. Where to Change Theme Colors & Styling
All colors and visual tokens are defined in:
👉 `src/styles/variables.css`

Example:
- **Background Base**: `--bg-primary: #0B0D0F;`
- **Surface / Card Background**: `--bg-surface: #181E24;`
- **Automotive Gold Accent**: `--accent-primary: #E8A317;`
- **Accent Hover**: `--accent-hover: #F8B324;`

---

### 4. Where to Update Vehicle Images
Place your vehicle images (.webp, .svg, .png, or .jpg) in:
👉 `public/images/bikes/`

Then reference the path in `src/data/bikes.ts` (e.g. `image: "/images/bikes/your-bike.webp"`).

---

### 5. Where to Edit FAQs & Rental Terms
- **FAQs**: `src/data/faqs.ts`
- **Rental Terms & Conditions**: `src/pages/Terms.tsx` (Items marked with `[EDIT: ...]` highlight customizable business policies).

---

## 🔒 Security & Architecture Notes
- Zero API keys are hardcoded in frontend code.
- Forms include validation with human-readable error banners.
- Pre-filled WhatsApp URLs are generated dynamically through `src/utils/whatsapp.ts`.
- The frontend booking flow is designed cleanly so a future backend (Node.js, Supabase, Firebase, or Laravel) can be connected without rewriting the UI.

---

## 📄 License
© 2026 Urban Rentals. All rights reserved.
