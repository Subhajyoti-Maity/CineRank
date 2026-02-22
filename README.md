
# CineRank – Modern Movies & People Discovery Platform

A modern React + Tailwind CSS app for discovering movies, TV series, and celebrities using real data from TMDB. Features rich browsing, progressive content reveal, glassmorphic UI, and Clerk authentication.

**Production Deployment:** https://cine-rank-f8zs.vercel.app/

---

## 🚀 Features
- Real Movie & TV Data (TMDB-powered)
- Browse popular celebrities, detailed biography, "Known For" credits
- Progressive sections: Weekly Picks, Popular Celebs, in-place expansion
- Advanced filter popover: multi-genre, language, rating/year sliders
- Stable routing IDs (`tmdbId`)
- Unified glassmorphic CTAs (`LiquidButton`)
- Responsive grid UI
- Local ratings (context + localStorage)
- Clerk authentication: drop-in auth UI, session management
- Context-driven state (`MovieContext`)
- Performance friendly: conditional rendering, chunked lists

---

## 🛠️ Tech Stack
- React 18
- React Router DOM
- Tailwind CSS
- Context API
- Custom Hooks
- TMDB API
- Axios
- PostCSS
- ESLint
- Font Awesome

---

## 📦 Installation & Setup

### Prerequisites
- Node.js 18+
- npm or yarn
- TMDB API key ([get one](https://www.themoviedb.org/settings/api))
- Clerk account ([get one](https://clerk.com/))

### Quick Start
1. Clone the repository:
   ```bash
   git clone https://github.com/Subhajyoti-Maity/CineRank.git
   cd CineRank
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Create `.env` file and add your keys:
   ```env
   REACT_APP_TMDB_API_KEY=your_tmdb_api_key
   REACT_APP_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
   ```
4. Start the development server:
   ```bash
   npm start
   ```
5. Open your browser at `http://localhost:3000`

### Build for Production
```bash
npm run build
```

### (Optional) Fix vulnerabilities
```bash
npm audit fix
npm audit fix --force
```

---

## 🏗️ Project Structure
```
CineRank/
├── api/
│   └── wishlist.js
├── build/
├── public/
│   ├── index.html
│   ├── robots.txt
│   └── sitemap.xml
├── src/
│   ├── App.css
│   ├── App.js
│   ├── components/
│   ├── context/
│   ├── data/
│   ├── hooks/
│   ├── pages/
│   ├── services/
│   └── utils/
├── .env
├── .gitignore
├── package.json
├── postcss.config.js
├── tailwind.config.js
├── vercel.json
├── README.md
├── SETUP.md
└── .vscode/
```

---

## 🎯 Key Concepts
- `movieService`: fetch logic for movies, TV, trending, people
- Stable IDs: `tmdbId` for routing
- `MovieContext`: global state
- Local storage hook: ratings/preferences
- Composable filters: genres, languages
- Routes: `/`, `/movies`, `/tv`, `/new`, `/top-rated`, `/people`, `/person/:id`, `/title/:id`, `/wishlist`, `/reviews`
- User menu (Clerk): `/wishlist`, `/reviews` from avatar dropdown
- Weekly Picks: curated, progressive reveal
- Popular Celebs: avatar grid, reveal increments
- Advanced filters: genre, language, year, rating
- Glass UI buttons: `LiquidButton`
- Movie & Person detail: rich meta sections

---

## 🔧 Configuration
### Environment Variables
```env
REACT_APP_TMDB_API_KEY=your_tmdb_api_key
REACT_APP_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
```

---

## 🤝 Contributing

Contributions are welcome! Please fork the repository and open a pull request.

Please ensure your code follows the project's style and passes all tests. If you have questions, open an issue before starting major work.

### 💬 Support
If you need help, have questions, or want to report an issue:
- Please open an issue on the GitHub repository for bug reports or feature requests.
- For direct contact, email the development team via the email address listed on the GitHub profile.

---

### 👤 Author
Subhajyoti Maity

