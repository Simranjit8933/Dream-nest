# DreamNest (MERN)
Stays marketplace with transparent pricing, no double bookings, verified-guest reviews and an AI Travel Copilot.
## Run
1. MongoDB running locally (or an Atlas URL in .env)
2. `cd server && npm i && cp .env.example .env` (fill JWT_SECRET and ANTHROPIC_API_KEY) `&& npm run seed && npm run dev`
3. `cd client && npm i && npm run dev`  -> http://localhost:5173
Demo host: host@demo.com / demo1234. Try the Copilot with: Plan a 3-day Manali trip under ₹12,000 for two people.
## Next steps
Host dashboard UI, image upload (Cloudinary), Razorpay payments, chat (Socket.io), deploy (Vercel + Render + Atlas).

## Map
Home page: **Show map** button (bottom) opens a list + map view; hovering a card highlights its pin. Listing page: **Where you'll be** map. Listings need `lat`/`lng` (the seed has them; hosts can send them to `POST /api/listings`). Run `npm i` in `client/` (adds leaflet + react-leaflet), then re-run `npm run seed`.

## Home page layout
Browsing (category "All", no search) shows rows of stays grouped by `place` ("Popular stays in Manali"); filtering or opening the map switches to the grid. A stay shows **Guest favourite** when it has 3+ reviews and a 4.8+ rating (rule: `fav()` in `client/src/pages.jsx`). Ratings in `seed.js` are demo values. Re-run `npm run seed` after updating.
