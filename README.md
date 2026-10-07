# CanteenQ: Canteen Pre-Order & Queue (MERN)

Order food from your phone, get a token, collect during your break.
Every order is valid for **one break only**, so the canteen cooks only what is ordered and food is not wasted.

**Stack:** MongoDB, Express, React (Vite), Node.js. Auth with JWT + bcrypt.

## Features
**Student:** register/login, pick a break, browse and search menu (category, veg filter), cart, place order, token + 4-digit pickup code, live status (Received, Cooking, Ready, Collected), queue position and wait estimate, cancel before cooking starts, order history.

**Canteen admin:** live order board (auto-refresh every 5s), start cooking / mark ready / hand over, verify token + code, prep sheet (how many of each item to cook), menu CRUD with stock and on/off switch, manage breaks, reports (revenue, popular items, orders per break, wasted-order rate).

**Anti-waste rules:** ordering closes before each break; slot capacity limit; max 2 active orders per student per break; uncollected orders auto-expire after the break plus a grace period; students with 3 no-shows must prepay; stock is reserved atomically and restored on cancel.

## Setup (once)
1. Install Node.js 18+ and MongoDB Community (or make a free MongoDB Atlas cluster and use its connection string).
2. Backend:
   ```
   cd server
   npm install
   (edit .env if you use Atlas)
   npm run seed
   npm run dev
   ```
3. Frontend (new terminal):
   ```
   cd client
   npm install
   npm run dev
   ```
4. Open http://localhost:5173

## Demo logins (created by seed)
- Student: student@college.com / student123
- Admin: admin@canteen.com / admin123

## Testing tip
Ordering closes `cutoff` minutes before a break starts. To demo at any time, log in as admin, open **Breaks**, and add a break starting about 30 minutes from now.

## Folder map
```
server/  models/ (User, MenuItem, Slot, Order, Counter)   routes/ (auth, menu, slots, orders)
         middleware/auth.js (JWT + admin check)           utils/expire.js (auto-expiry job)
client/  src/pages/ (Auth, Menu, Checkout, Orders, Admin*) src/context.jsx (user + cart state)
```
