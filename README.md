# KBC+ — Kaun Banega Crorepati (Full Stack)
> Node.js + Express + MongoDB + React

---

## 🚀 Setup in 5 Steps

### Step 1 — Make sure you have these installed
- Node.js (v16+)
- MongoDB (running locally on port 27017)
- npm

---

### Step 2 — Backend Setup

```bash
cd kbc-plus/backend
npm install
```

---

### Step 3 — Seed the Database (30 questions)

```bash
npm run seed
```

You should see: `✅ Seeded 30 questions successfully!`

---

### Step 4 — Start Backend Server

```bash
npm run dev
# OR
npm start
```

You should see:
```
🚀 Server running on port 5000
✅ MongoDB Connected
```

---

### Step 5 — Frontend Setup (new terminal)

```bash
cd kbc-plus/frontend
npm install
npm start
```

Opens at: http://localhost:3000

---

## 🎮 How to Play

1. Enter your name → Click Start Game
2. Answer questions across 10 levels
3. Timer counts down (30s early, 20s mid, 15s late levels)
4. Use lifelines wisely (once each):
   - ❌ **Remove Weakest** — removes 1 wrong option
   - ⏸️ **Time Freeze** — pauses timer for 15 seconds
   - 🔁 **Flip Question** — loads a new question of same level
5. Quit anytime to keep your current score
6. Safe zones at Level 3, 6, and 9

---

## 🗃️ CRUD Operations

| Operation | Where | Route |
|-----------|-------|-------|
| **Create** | Save player after game | POST /api/players |
| **Create** | Add question (seed) | POST /api/questions |
| **Read** | Fetch question by level | GET /api/questions/level/:level |
| **Read** | Leaderboard | GET /api/players |
| **Update** | Update player high score | POST /api/players (upsert) |
| **Delete** | Delete player from leaderboard | DELETE /api/players/:id |
| **Delete** | Delete a question | DELETE /api/questions/:id |

---

## 📁 Project Structure

```
kbc-plus/
├── backend/
│   ├── models/
│   │   ├── Question.js       ← MongoDB schema
│   │   └── Player.js         ← MongoDB schema
│   ├── routes/
│   │   ├── questions.js      ← Full CRUD routes
│   │   └── players.js        ← CRUD routes
│   ├── server.js             ← Express app
│   ├── seed.js               ← 30 seeded questions
│   └── .env                  ← MongoDB URI
└── frontend/
    └── src/
        ├── pages/
        │   ├── Home.jsx       ← Name entry + start
        │   ├── Game.jsx       ← Main game logic
        │   └── Leaderboard.jsx← Top 10 + delete
        ├── components/
        │   └── Timer.jsx      ← Countdown ring
        └── App.jsx            ← Routes
```

---

## 🏆 Prize Ladder

| Level | Points | Safe Zone |
|-------|--------|-----------|
| 1  | ₹100      | — |
| 2  | ₹200      | — |
| 3  | ₹500      | ✅ |
| 4  | ₹1,000    | — |
| 5  | ₹2,000    | — |
| 6  | ₹4,000    | ✅ |
| 7  | ₹8,000    | — |
| 8  | ₹16,000   | — |
| 9  | ₹32,000   | ✅ |
| 10 | ₹1,00,000 | 🏆 |
