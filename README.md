# Masterbank (BankingApp-React)

Masterbank is a React single-page application for managing banking customers, accounts, and transactions. It connects to a REST API for authentication, account data, transfers, deposits, and auditor operations.

Key features

- Authentication: register, login, logout, forgot/reset password
- Role-based access: CUSTOMER, ADMIN, AUDITOR (client-side guards)
- Profile management: view/update profile, upload profile picture
- Account operations: view accounts, view transactions, paginated transaction lists
- Transfers: make inter-account transfers
- Deposits / Auditor actions: auditor/admin-only deposit and audit dashboards
- Routing: react-router-dom used for navigation and protected routes
- API integration: axios instance with token interceptor (src/services/api.js)

Quickstart

Prerequisites
- Node.js (>= 16 recommended)
- npm

Install

1. Open a terminal in this folder (masterbank)
2. Install dependencies:

   npm install

Run (development)

   npm start

Open http://localhost:3000 in your browser. The app supports hot reload during development.

Build (production)

   npm run build

Tests

   npm test

Configuration

- API base URL is defined in src/services/api.js via the API_BASE_URL constant. Change it to point to your backend when necessary.
- Auth tokens and roles are stored in localStorage by the apiService. Ensure the backend returns { data: { token, roles } } on login.

Important files and folders

- src/services/api.js — axios instance, auth helpers, API methods (login, register, transactions, audit endpoints)
- src/services/Guard.js — CustomerRoute and AuditorRoute wrappers for protected routes
- src/pages — page components (Home, Login, Register, Profile, Transactions, Transfer, AuditorDashboard, Deposit, etc.)
- src/components — shared components (Navbar, Footer)
- public — static assets and index.html

Scripts

- npm start — run dev server
- npm run build — create optimized production build
- npm test — run test runner
- npm run eject — eject CRA config (one-way)

Deployment

Build the app with npm run build and serve the /build folder with any static hosting (Netlify, Vercel, S3 + CloudFront, or a traditional web server).

Security notes

- Client-side role checks are convenience guards — always enforce authorization on the server.
- Avoid committing secrets into the codebase. Use environment variables or CI/CD secrets for production configuration.

Contribution

Contributions welcome. Open an issue or PR with a clear description and tests where applicable.

License

Specify project license here (e.g., MIT).

Contact

support@masterbank.com
(https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)
