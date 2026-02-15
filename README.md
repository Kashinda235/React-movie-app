# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Babel](https://babeljs.io/) (or [oxc](https://oxc.rs) when used in [rolldown-vite](https://vite.dev/guide/rolldown)) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## React Compiler

The React Compiler is not enabled on this template because of its impact on dev & build performances. To add it, see [this documentation](https://react.dev/learn/react-compiler/installation).

## Expanding the ESLint configuration

If you are developing a production application, we recommend using TypeScript with type-aware lint rules enabled. Check out the [TS template](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) for information on how to integrate TypeScript and [`typescript-eslint`](https://typescript-eslint.io) in your project.

# 🎬 Movie Pro: Trending Movies & Search

A modern React application that allows users to search for movies and tracks "Trending" titles using **Appwrite** as a backend-as-a-service.

## 🚀 Features

* **Live Movie Search:** Fetches real-time data using the TMDB API.
* **Trending Algorithm:** Tracks how many times a movie is searched and displays the top results.
* **Appwrite Integration:** Uses Appwrite Databases and Collections to store search metrics.
* **Responsive Design:** Fully functional on mobile, tablet, and desktop.

---

## 🛠️ Tech Stack

* **Frontend:** React.js, Tailwind CSS, Vite
* **Backend:** [Appwrite Cloud](https://cloud.appwrite.io/)
* **API:** The Movie Database (TMDB)

---

## ⚙️ Setup & Installation

### 1. Clone the Repository

```bash
git clone https://github.com/Kashinda235/React-movie-app.git
cd React-movie-app

```

### 2. Install Dependencies

```bash
npm install

```

### 3. Environment Variables

Create a `.env` file in the root directory and add your keys:

```env
VITE_TMDB_API_KEY=your_tmdb_api_key
VITE_APPWRITE_PROJECT_ID=your_project_id
VITE_APPWRITE_DATABASE_ID=your_database_id
VITE_APPWRITE_COLLECTION_ID=metrics

```

### 4. Appwrite Configuration (Crucial)

To avoid **CORS** and **Unauthorized** errors, ensure your Appwrite console is configured as follows:

* **Platform:** Under *Project Settings > Integrations*, add a **Web App** with the hostname `localhost`.
* **Permissions:** Under *Database > metrics > Settings*, add a Role for **Any** and grant it **Read** and **Create** permissions.
* **Attributes:** Ensure your `metrics` table has the following attributes:
* `searchTerm` (String)
* `count` (Integer)
* `movie_id` (Integer or String)
* `poster_url` (String)



---

## 🏃‍♂️ Running the App

```bash
npm run dev

```

The app will be available at `http://localhost:5173`.

---

## 💡 Troubleshooting Tips

* **CORS Error:** Double-check that your **Endpoint** in `appwrite.js` matches your project's region (e.g., Singapore vs. Frankfurt).
* **401 Unauthorized:** Ensure you saved the "Read" permissions for the **Any** role in your collection settings.
* **Environment Variables:** If you edit your `.env` file, you **must restart** the development server (`npm run dev`).

---

## 📄 License

This project is open-source and available under the MIT License.

---
