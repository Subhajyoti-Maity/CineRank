# CineRank – Modern Movies & People Discovery Platform

A modern React + Tailwind application for discovering movies, TV series, and popular celebrities (people) using real data from The Movie Database (TMDB). The platform emphasizes rich browsing, people exploration, progressive content reveal sections, a refined glassmorphic UI, and first‑class authentication with Clerk.

Production Deployment: <https://cinerank-tau.vercel.app>

---

## 🚀 Core Features
- **Real Movie & TV Data**: TMDB-powered (movies, TV series, trending, upcoming, now playing)
- **People / Celebs Module**: Browse popular celebrities and view detailed biography + "Known For" credits
- **Progressive Sections**: Weekly Picks & Popular Celebs with in-place "See more" expansion (no page reload/navigation)
- **Advanced Filter Popover**: Multi-genre selection, language filtering, rating/year sliders, clear & apply controls
- **Stable Routing IDs**: Internal `tmdbId` for correct detail navigation
- **Unified Glass Buttons**: Reusable `LiquidButton` component for consistent glassmorphic CTAs
- **Modern Grid UI**: Responsive, accessible layouts with expressive headings
- **Local Ratings (Extensible)**: Context + localStorage patterns for personalization
- **Authentication with Clerk**: Drop-in auth UI, session management, and a personalized user dropdown
- **Context-driven State**: Central `MovieContext` aggregates movies, TV, people & details
- **Performance Friendly**: Conditional rendering, chunked lists, progressive reveal

---

## 🛠️ Tech Stack
- **React 18**
- **React Router DOM**
- **Tailwind CSS**
- **Context API**
- **Custom Hooks**
- **TMDB API**
- **Axios**
- **PostCSS**
- **ESLint**
- **Font Awesome**

---

## 📦 Installation & Setup

### Prerequisites
- Node.js 18+
- npm or yarn
- TMDB API key (free from [themoviedb.org](https://www.themoviedb.org/settings/api))
- Clerk account (free) with a Publishable Key

### Repository
GitHub: [https://github.com/Subhajyoti-Maity/CineRank.git](https://github.com/Subhajyoti-Maity/CineRank.git)

### Quick Start
1. **Clone the repository:**
   ```bash
   git clone https://github.com/Subhajyoti-Maity/CineRank.git
   cd CineRank
   ```
2. **Install dependencies:**
   ```bash
   npm install
   ```
3. **Create environment file:**
   ```bash
   touch .env
   ```
   Add your keys (replace values with your own):
   ```env
   REACT_APP_TMDB_API_KEY=your_tmdb_api_key
   REACT_APP_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
   ```
4. **Start the development server:**
   ```bash
   npm start
   ```
5. **Open your browser:**
   Navigate to `http://localhost:3000`

### Building for Production
```bash
npm run build
```

### (Optional) Fix vulnerabilities
If you see npm warnings about vulnerabilities, you can try:
```bash
npm audit fix
```
or
```bash
npm audit fix --force
```

---

## 🏗️ Project Structure (Key Paths)
```
CineRank/
├── api/
│   └── wishlist.js
├── build/                # Production build output (auto-generated)
├── public/
│   ├── favicon.png
│   ├── index.html
│   ├── mm.png
│   ├── robots.txt
│   └── sitemap.xml
├── src/
│   ├── App.css
│   ├── App.js
│   ├── index.js
│   ├── components/
│   │   ├── ErrorBoundary.js
│   │   ├── FilterPopover.js
│   │   ├── Footer.js
│   │   ├── Header.js
│   │   ├── Hero.js
│   │   ├── LiquidButton.js
│   │   ├── MovieCard.js
│   │   ├── MovieModal.js
│   │   ├── MoviesGrid.js
│   │   ├── MultiGenreFilter.js
│   │   ├── PersonCard.js
│   │   ├── PopularCelebsSection.js
│   │   ├── StarRating.js
│   │   ├── TrailerModal.js
│   │   └── WeeklyPicks.js
│   ├── context/
│   │   ├── AuthContext.js
│   │   ├── MovieContext.js
│   │   └── WishlistContext.js
│   ├── data/
│   │   └── cinerank.png
│   ├── hooks/
│   │   └── useLocalStorage.js
│   ├── pages/
│   │   ├── HomePage.js
│   │   ├── MovieDetailPage.js
│   │   ├── MoviesPage.js
│   │   ├── NewReleasesPage.js
│   │   ├── PeoplePage.js
│   │   ├── PersonDetailPage.js
│   │   ├── ReviewsPage.js
│   │   ├── TopRatedPage.js
│   │   ├── TvSeriesPage.js
│   │   └── WishlistPage.js
│   ├── services/
│   │   ├── imdbService.js
│   │   ├── movieService.js
│   │   └── tmdbService.js
│   ├── utils/
│   │   └── releaseMeta.js
├── .env
├── .gitignore
├── package.json
├── package-lock.json
├── postcss.config.js
├── tailwind.config.js
├── vercel.json
├── README.md
├── SETUP.md
└── .vscode/
    └── tasks.json
```

---

## 🎯 Key Concepts & Components
- **movieService**: Consolidates fetch logic for movies, TV, trending, upcoming, people & person details
- **Stable IDs**: Transformer adds `tmdbId` to ensure consistent routing and key usage
- **MovieContext**: Global state for movies, TV, people, details
- **Local Storage Hook**: For persisting ratings/user preferences
- **Composable Filters**: Dynamic genre & language lists from API
- **Routes**: `/`, `/movies`, `/tv`, `/new`, `/top-rated`, `/people`, `/person/:id`, `/title/:id`, `/wishlist`, `/reviews`
- **User Menu (Clerk)**: `/wishlist`, `/reviews` available from avatar dropdown
- **Weekly Picks**: Curated section revealed row-by-row
- **Popular Celebs**: Circular avatar grid with reveal increments
- **Advanced Filters**: Multi-genre, language, year, and rating range
- **Glass UI Buttons**: `LiquidButton` variants unify CTAs
- **Movie & Person Detail**: Rich meta sections (biography, departments, known for)

---

## 🔧 Configuration
### Environment Variables
Client-side (CRA):
```env
REACT_APP_TMDB_API_KEY=your_tmdb_api_key
REACT_APP_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
```

---

## 🤝 Contributing
1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 📞 Support
If you have any questions or need help setting up the project, please create an issue in the repository or contact the development team.

---

Built with ❤️ using modern web technologies.
