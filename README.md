# 🌍 TerraFlag — World Flag Quiz

An interactive, responsive full-stack geography quiz built with **Node.js**, **Express**, **PostgreSQL**, and **EJS**. Test your knowledge of national flags around the world, maintain high-score streaks, and climb the ranks from Novice Scout to Master Geographer!

---

## ✨ Features

- **Dynamic Database Integration**: Flags and country data are queried dynamically from a PostgreSQL relational database.
- **Score Streak Counter**: Real-time score tracking keeping count of correct consecutive guesses.
- **Neo-Arcade UI / UX**: Modern dark theme with ambient lighting, glassmorphic cards, custom typography (`Bricolage Grotesque` & `Space Grotesk`), and tactile micro-interactions.
- **Tiered Rank Rating**: Dynamic explorer ranking (Novice Scout, Explorer, Global Navigator, Master Geographer) based on run performance.
- **Responsive Layout**: Designed for seamless gameplay across mobile devices, tablets, and desktops.

---

## 🛠️ Tech Stack

- **Backend**: [Node.js](https://nodejs.org/), [Express.js](https://expressjs.com/)
- **Database**: [PostgreSQL](https://www.postgresql.org/) (`pg` client)
- **Frontend / Templating**: [EJS (Embedded JavaScript)](https://ejs.co/), Modern CSS3 (CSS Variables, Flexbox, Glassmorphism)
- **Parsing & Utilities**: `body-parser`

---

## 🚀 Getting Started

### 1. Prerequisites

- [Node.js](https://nodejs.org/) (v16+ recommended)
- [PostgreSQL](https://www.postgresql.org/download/) installed and running locally

### 2. Database Setup

1. Open your PostgreSQL terminal (`psql`) or pgAdmin and create a database named `world`:
   ```sql
   CREATE DATABASE world;
   ```
2. Connect to the `world` database:
   ```sql
   \c world
   ```
3. Create the `flags` table:
   ```sql
   CREATE TABLE flags (
       id SERIAL PRIMARY KEY,
       name VARCHAR(100),
       flag VARCHAR(10)
   );
   ```
4. Import the country flags from `flags.csv`:
   ```sql
   \copy flags FROM 'flags.csv' DELIMITER ',' CSV HEADER;
   ```

### 3. Configure Database Credentials

In `index.js`, configure your PostgreSQL connection settings:

```javascript
const db = new pg.Client({
  user: "postgres",
  host: "localhost",
  database: "world",
  password: "YOUR_POSTGRES_PASSWORD",
  port: 5432,
});
```

### 4. Installation & Launch

Install project dependencies:
```bash
npm install
```

Start the application:
```bash
node index.js
```

Open your browser and navigate to:
```
http://localhost:3000
```

---

## 📂 Project Structure

```
├── public/
│   ├── images/
│   │   └── background.jpg     # Background canvas image
│   └── styles/
│       └── main.css           # Custom styling and design system
├── views/
│   └── index.ejs              # Main quiz and game-over template
├── flags.csv                  # Dataset of country names and unicode flags
├── index.js                   # Express server and database queries
├── package.json               # Project metadata and dependencies
└── README.md                  # Project documentation
```

---

## 📄 License

This project is open-source and available under the [ISC License](LICENSE).
