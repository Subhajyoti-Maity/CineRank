
# CineRank – Modern Movies & People Discovery Platform

A modern React + Tailwind application for discovering movies, TV series, and popular celebrities (people) using real data from The Movie Database (TMDB). The platform now emphasizes rich browsing, people exploration, progressive content reveal sections, a refined glassmorphic UI, and first‑class authentication with Clerk.

## 🌐 Live Demo

Production Deployment: <https://cinerank-tau.vercel.app>

> If the link 404s shortly after a new deploy, wait a few seconds and refresh while DNS / CDN edges propagate.

## 🚀 Core Features

- **Real Movie & TV Data**: TMDB-powered (movies, TV series, trending, upcoming, now playing)
- **People / Celebs Module**: Browse popular celebrities and view detailed biography + "Known For" credits
- **Progressive Sections**: Weekly Picks & Popular Celebs with in-place "See more" expansion (no page reload/navigation)
- **Advanced Filter Popover**: Multi-genre selection, language filtering, rating/year sliders, clear & apply controls
- **Stable Routing IDs**: Added internal `tmdbId` to ensure correct detail navigation (fixes mismatched pages)
- **Unified Glass Buttons**: Reusable `LiquidButton` component for consistent glassmorphic CTAs
- **Modern Grid UI**: Responsive, accessible layouts with consistent spacing & large expressive headings
- **Local Ratings (Extensible)**: Context + localStorage patterns ready for persistent personalization
- **Authentication with Clerk**: Drop-in auth UI, session management, and a personalized user dropdown
   - User dropdown now includes: Wishlist and Reviews (via Clerk)
   - Header cleaned up: Wishlist button removed; access via user menu
   - Clerk authentication UI and dropdown now match the site's dark theme
- **Context-driven State**: Central `MovieContext` aggregates movies, TV, people & details
- **Performance Friendly**: Conditional rendering, chunked lists, progressive reveal

> Header no longer shows a standalone Wishlist link; use the user dropdown (Clerk) for Wishlist and Reviews.
> Clerk SignIn/SignUp and dropdown are themed to match the site's dark mode for a seamless experience.

## 🛠️ Tech Stack

### Frontend

- **React 18** - Modern React with functional components and hooks
- **React Router DOM** - Client-side routing and navigation
- **Tailwind CSS** - Utility-first CSS framework for styling
- **Context API** - Global state management
- **Custom Hooks** - Reusable logic with localStorage integration


### API & Services

- **TMDB API** - The Movie Database API for real movie data
- **Axios** - HTTP client for API requests
- **Service Layer** - Organized API service architecture


### Development Tools

- **PostCSS** - CSS processing with Autoprefixer
- **ESLint** - Code linting and formatting
- **Font Awesome** - Icon library

## 📦 Installation & Setup


### Prerequisites

- Node.js 18+
- npm or yarn
- TMDB API key (free from [themoviedb.org](https://www.themoviedb.org/settings/api))
- Clerk account (free) with a Publishable Key (client) and Secret Key (server)


### Repository

GitHub: [https://github.com/Subhajyoti-Maity/CineRank.git](https://github.com/Subhajyoti-Maity/CineRank.git)

### Quick Start

1. **Clone the repository:**

   ```bash
   git clone <repository-url>
   cd CineRank
   ```

2. **Install dependencies:**

   ```bash
   npm install
   ```

3. **Create environment file:**

   Create a `.env` file in the project root:

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


## 🎯 Key Concepts & Components

### API & Data

- **movieService**: Consolidates fetch logic for movies, TV, trending, upcoming, people & person details
- **Stable IDs**: Transformer adds `tmdbId` to ensure consistent routing and key usage
- **Combined Credits**: Person detail page uses merged credits to power "Known For" section


### State Management

- **MovieContext**: Extended to include `popularPeople`, `personDetails`, plus existing movie & TV slices
- **Local Storage Hook**: Ready for persisting ratings/user preferences
- **Composable Filters**: Dynamic genre & language lists populated from API


### Routing & Navigation

- **Routes**: `/`, `/movies`, `/tv`, `/new`, `/top-rated`, `/people`, `/person/:id`, `/title/:id`, `/wishlist`, `/reviews`
- **User Menu (Clerk)**: `/wishlist`, `/reviews` are available from the avatar dropdown (Clerk)
- **Deep Linking**: Stable detail page URLs using TMDB IDs

### User-Facing Features

- **Weekly Picks**: Curated section revealed row-by-row (5 items per expansion)
- **Popular Celebs**: Circular avatar grid with +5 reveal increments after first 10
- **Advanced Filters**: Multi-genre, language, year, and rating range (popover UI)
- **Glass UI Buttons**: `LiquidButton` variants (primary / ghost) unify CTAs
- **Movie & Person Detail**: Rich meta sections (biography, departments, known for)


## 🎨 Styling & Design


### Tailwind CSS Integration

### Clerk Dark Theme

- Clerk SignIn/SignUp and dropdown are themed to match the site's dark mode using appearance variables and custom CSS for a seamless look.

### Responsive Breakpoints


## 🔧 Configuration

### Environment Variables

Client-side (CRA):

```bash
REACT_APP_TMDB_API_KEY=your_tmdb_api_key
REACT_APP_CLERK_PUBLISHABLE_KEY=pk_test_...
```

Server-side / serverless (do not expose):

```bash
CLERK_SECRET_KEY=sk_test_...
```

Notes:

- The app entry reads the publishable key from `REACT_APP_CLERK_PUBLISHABLE_KEY`.
- Never commit real secrets. Prefer `.env.local` for personal values and keep templates in `.env.local.example`.

### Tailwind Configuration

The project includes custom Tailwind configuration with:

- Extended color palette
- Custom animations
- Dark mode support
- Responsive breakpoints

## 🚀 Features in Detail (Expanded)

### TMDB & People Integration

- Popular, top-rated, trending (daily/weekly), upcoming, now-playing movies
- TV series category support
- Popular People list + individual person detail (bio, departments, known for credits)
- Stable link generation via `tmdbId`
- Poster/profile image handling with graceful fallback

### User Experience & UI

- **Progressive Reveal**: Incremental content avoids overwhelming the user
- **Glassmorphic Buttons**: Consistent interaction affordances
- **Responsive Grids**: Optimized layout at 2 / 3 / 5 column breakpoints
- **Hover Micro-interactions**: Subtle scale + ring effects on avatars/cards
- **Error & Empty States**: Safe-guards for missing profiles, ids, or data chunks

### Performance Considerations

- Chunked list rendering (rows of 5)
- Avoids unnecessary re-renders via memoized groups
- Minimal external dependencies (hand-rolled `cx` helper)
- Conditional feature rendering to reduce initial payload


## 🔮 Future Scope & Improvements

- **Wishlist & Reviews Expansion**: Add ability to create, edit, and share wishlists and reviews with other users. Enable rating and commenting on reviews.
- **Social Features**: Follow users, see friends' activity, and share recommendations.
- **Notifications**: Add in-app and email notifications for new releases, reviews, and wishlist updates.
- **Admin Dashboard**: Manage content, users, and moderate reviews.
- **Mobile App**: Build a React Native version for iOS/Android.
- **Performance**: Add server-side rendering (SSR) or static site generation (SSG) for SEO and speed.
- **Accessibility**: Further improve keyboard navigation and screen reader support.
- **Internationalization**: Add multi-language support for global users.
- **Testing**: Add more unit and integration tests for critical flows.

## 🧭 Changelog (Recent)

### 2025-10 (Clerk Auth & Menu Cleanup)
- Migrated authentication to Clerk
- Removed legacy login modal and unused code
- Added Wishlist and Reviews to Clerk dropdown
- Themed Clerk UI and dropdown to match site dark mode

### 2025-09 (People & UI Expansion)
- Added Popular Celebs section
- Improved progressive reveal and grid layouts
- Refined glassmorphic UI and button system

### Earlier (Foundational)


## 🤝 Contributing

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.


## 🙏 Acknowledgments



## 📞 Support

If you have any questions or need help setting up the project, please create an issue in the repository or contact the development team.



Built with ❤️ using modern web technologies.
