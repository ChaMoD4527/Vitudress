# Vitudress

Full-stack monorepo for an e-commerce style “virtual dress” app.
- **Frontend:** React + CRACO + Tailwind
- **Backend:** Node.js + Express + MongoDB (JWT auth, basic CRUD)
- **Repo layout:** single Git repo with `frontend/` and `backend/`

## Features
- Auth (register, login, protected routes)
- Product catalog and orders
- Contact form
- Responsive UI with Tailwind
- API helpers and Redux slice for auth

## Tech Stack
**Frontend:** React 18, React Router, Redux Toolkit, Tailwind, CRACO  
**Backend:** Node 20+, Express, Mongoose, JSON Web Tokens  
**Tooling:** npm, GitHub Actions (optional)

## Monorepo Structure

.
├─ backend/
│ ├─ models/ (User, Product, Order, Contact)
│ ├─ routes/ (auth, user, contact)
│ ├─ utils/ (cdnHelper.js)
│ ├─ server.js
│ └─ package.json
├─ frontend/
│ ├─ public/
│ ├─ src/
│ │ ├─ pages/ (Home, Pricing, Purchase, Dashboard, About, Contact, Auth)
│ │ ├─ components/ (Header, Footer, ProtectedRoute)
│ │ ├─ contexts/ (AuthContext)
│ │ ├─ store/ (slices/authSlice.js)
│ │ └─ utils/ (api.js)
│ └─ package.json
└─ README.md


## Prerequisites
- Node.js 20+ and npm
- MongoDB URI (Atlas or local)
- Git

## Quick Start
Clone and install:
```bash
git clone https://github.com/ChaMoD4527/Vitudress.git
cd Vitudress

# Backend
cd backend
npm install
cp .env.example .env   # create and fill values
npm run dev            # starts backend (nodemon if configured)

# Frontend (new terminal)
cd ../frontend
npm install
npm start              # starts React dev server



Default Dev URLs

Frontend: http://localhost:3000

Backend: http://localhost:5000
 (configurable)

Environment Variables

Create the files below.

backend/.env

PORT=5000
MONGODB_URI=mongodb+srv://<user>:<pass>@<cluster>/<db>?retryWrites=true&w=majority
JWT_SECRET=change-me
CDN_KEY=optional-or-remove


frontend/.env

REACT_APP_API_BASE=http://localhost:5000

NPM Scripts

Backend (/backend)

npm run dev – start with hot reload

npm start – start production

npm run lint – optional lint

Frontend (/frontend)

npm start – dev server

npm run build – production build

npm test – tests (if used)

API Overview (backend)

Base: /api

POST /api/auth/register – create account

POST /api/auth/login – get JWT

GET /api/user/me – profile (requires Authorization: Bearer <token>)

POST /api/contact – submit contact form

GET/POST/PUT/DELETE /api/products – products (if enabled)

Development Notes

Do not commit secrets or node_modules/. See .gitignore.

Uploaded files belong in backend/uploads/ and are ignored.

Line endings normalized via .gitattributes (LF for code).

Build & Deploy (basic)

Frontend:

cd frontend
npm run build
# upload /frontend/build to hosting (Netlify/Vercel/static host)


Backend:

cd backend
npm ci
NODE_ENV=production node server.js
# set env vars on your host (PORT, MONGODB_URI, JWT_SECRET)

Troubleshooting

Windows CRLF warnings → run once:

git add --renormalize .
git commit -m "Normalize line endings"


CORS errors → set frontend REACT_APP_API_BASE to the deployed backend URL and enable CORS on the server.

Roadmap

Product images via stable CDN

Admin dashboard

Payment integration

Contributing

Create a branch: git checkout -b feature/<name>

Commit: git commit -m "feat: ..."

Push: git push -u origin feature/<name>

Open a PR

License

See LICENSE
.


If you want badges or screenshots, tell me which ones and I will add them.



