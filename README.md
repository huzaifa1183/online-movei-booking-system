# 🎬 CineVault — Premium Movie Booking Web App

CineVault is a fully client-side, single-file movie ticket booking application. It simulates a complete cinema booking experience — from browsing movies to selecting seats, paying, and downloading a digital ticket — entirely in the browser with no backend required.

---

## ✨ Features

### 🏠 Home / Movie Listing
- Grid of **50 movies** (Hollywood, Bollywood, Animation, Horror, Sci-Fi, etc.) with posters, ratings, duration, and genre tags.
- **Live search** by movie name or genre.
- **Genre filter chips** (All, Action, Drama, Sci-Fi, Horror, Comedy, Thriller, Animation, Bollywood).
- Graceful **poster fallback** (emoji placeholder) if an image fails to load.
- "NEW" / "HOT" badges on trending titles.

### 🎞️ Movie Detail Page
- Hero banner with blurred poster background.
- Movie synopsis, genre/rating/duration tags.
- Embedded **YouTube trailer**.
- **Cast & crew** cards.
- **Showtime picker** across multiple dates and slots.

### 💺 Seat Selection
- Visual cinema **seat map** with Premium / Standard / Economy pricing rows.
- Real-time **available / booked / selected** seat states.
- Dynamic price calculation based on row category.
- Max 8 seats per booking, with live footer summary.

### 🧾 Booking Flow
- **Step indicator** (Seats → Summary → Payment → Confirmation).
- **Booking Summary** with subtotal, convenience fee, GST (18%), and total.
- **10-minute seat hold countdown timer**.
- **Payment page** (test mode) with card number/expiry formatting, validation, and a fake multi-stage "processing" animation.
- **Confirmation page** with a styled digital ticket, unique booking ID, and barcode.
- **Downloadable/printable ticket** (opens a print-ready HTML ticket in a new tab).

### 🔐 Auth
- Login / Register modal with tabbed UI (client-side only, no real backend — any credentials work).
- Nav bar updates to show logged-in user with logout option.

### 🎨 UX Details
- Dark cinematic theme with gold/teal accent colors, custom fonts (Bebas Neue, DM Sans, Oswald).
- Toast notification system (success / error / info).
- Fully **responsive** layout (mobile hamburger nav, adaptive grid, seat sizing).
- Smooth fade-in animations and hover transitions throughout.

---

## 🛠️ Tech Stack

- **HTML5 / CSS3** — single-file styling with CSS variables for theming.
- **Vanilla JavaScript (ES6)** — no frameworks, no build step.
- **Google Fonts** — Bebas Neue, DM Sans, Oswald.
- **TMDB image CDN** — used for movie poster URLs.

No npm install, no bundler, no server — just open the HTML file in a browser.

---

## 📂 Project Structure

Since this is a self-contained single file:

```
cinevault.html   → contains all HTML, CSS, and JavaScript
```

Everything (movie data, seat maps, booking logic, UI rendering) lives inside this one file for easy portability.

---

## 🚀 Getting Started

1. Download `cinevault.html`.
2. Open it directly in any modern browser (Chrome, Edge, Firefox, Safari).
3. No installation, server, or dependencies required.

> Optional: Serve it via a simple local server (e.g. `npx serve` or Python's `http.server`) if you want proper relative-path behavior, though it's not required since everything is inline.

---

## 🧩 Key Data Structures (in `script`)

| Object | Purpose |
|---|---|
| `MOVIES[]` | Array of 50 movie objects (id, name, genre, poster, cast, showtimes, pricing, etc.) |
| `BOOKED_SEATS[]` | Hardcoded list of already-booked seat IDs for demo purposes |
| `state{}` | Central app state — selected movie, date/time, seats, prices, user, booking ID |

---

## ⚠️ Notes / Limitations

- This is a **frontend demo/prototype** — there is no real backend, database, or payment gateway. All bookings, logins, and payments are simulated in-browser and reset on page reload.
- Poster images are pulled from TMDB's CDN — if a path is invalid or offline, an emoji placeholder is shown instead.
- "Any email + password" works for login/register since there's no real authentication.
- Card payment always succeeds after the simulated processing delay (no real validation beyond basic format checks).

---

## 📌 Possible Next Steps

- Connect to a real backend (Node/Express, Firebase, Supabase) for persistent bookings and auth.
- Integrate an actual payment gateway (Stripe/Razorpay).
- Pull live movie data from a real API (e.g., TMDB API) instead of a static array.
- Add user booking history / "My Bookings" page.
- Add real seat-lock concurrency handling for multi-user booking.

---

## 📄 License

Free to use and modify for personal or educational projects.
