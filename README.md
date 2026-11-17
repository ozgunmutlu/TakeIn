# Take-In

**A web application promoting sustainable food practices through community sharing.**

**Take-In** is a social web app designed to encourage sustainable food consumption and reduce food waste. Users can share recipes, leftover ingredients, and engage with others to build a conscious culinary community.

Built using **Node.js**, **Express**, **MongoDB**, and **EJS**, the platform integrates user authentication, social features, and real-time interactivity — all tailored for a mobile-friendly web experience.

---

## Key Features

- **User Authentication:** Secure login system using Passport.js and bcrypt.
- **Recipe Sharing:** Users can create, view, and favorite recipes, complete with ratings and Nutri-Scores.
- **Smart Shopping Cart:** Add recipes for custom serving sizes and compile a shopping list.
- **Chat & Friends System:** Connect and message other users; see mutual friends and community ratings.
- **Leftover Map:** Share or claim leftover ingredients via an interactive list.
- **Community Ratings:** Rate both recipes and users based on interaction and reliability.
---



### Prerequisites

- Node.js (v18 or higher)
- MongoDB, either:
  - **Local:** [MongoDB Community Server](https://www.mongodb.com/try/download/community), installed as a service so it runs in the background, or
  - **Cloud:** a free [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) cluster

### Installation

```bash
git clone https://github.com/ozgunmutluu/R-D-Project-Take-In.git
cd R-D-Project-Take-In/TakeIn
npm install
```

Create a `.env` file **inside the `TakeIn` folder** (next to `index.js` and `package.json`):

```
MONGODB_STRING=mongodb://127.0.0.1:27017/takein
SESSION_SECRET=your_long_random_secret
PORT=8000
```

- `MONGODB_STRING`: keep the value above for a local MongoDB. For Atlas, use your cluster's connection string instead (`mongodb+srv://<user>:<password>@<cluster>.mongodb.net/takein?retryWrites=true&w=majority`).
- `SESSION_SECRET`: any long random string. You can generate one with:
  ```bash
  node -e "console.log(require('crypto').randomBytes(64).toString('hex'))"
  ```

`.env` is listed in `.gitignore`, so it is never committed.

### Running the App

Make sure MongoDB is running, then from the `TakeIn` folder:

```bash
npm start
```

Then visit: [http://localhost:8000](http://localhost:8000). The terminal should show `Database connected`.

### Troubleshooting

- **`The uri parameter to openUri() must be a string, got "undefined"`**: `.env` is missing, is in the wrong folder, or uses a different variable name. It must be `TakeIn/.env` and contain `MONGODB_STRING=...`.
- **`connect ECONNREFUSED 127.0.0.1:27017`**: MongoDB isn't running. On Windows, run `net start MongoDB` in an administrator terminal, or install MongoDB Community Server as a service.
- nodemon doesn't restart when `.env` changes. Stop it with `Ctrl+C` and run `npm start` again.
