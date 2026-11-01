# BugRepo Frontend

React frontend for **BugRepo**, a bug reporting and reproduction tracking application for QA engineers and developers.

**Backend:** [bugrepo-backend](https://github.com/deepikarthinikanche/bugrepo-backend)

## Features

- User registration and login with role-based access.
- Dashboard for viewing bug reports and status statistics.
- Bug reporting with reproduction steps, expected and actual results, priority, and environment details.
- Automatic detection of browser and operating system information.
- Bug assignment and status updates.
- Step-by-step reproduction playback.
- Bug insights, including priority suggestions, root-cause hints, possible duplicates, and Playwright script drafts.
- Export bug reports and insight reports.
- Responsive layout.

## Tech stack

- React 18
- React Router
- Context API
- Axios
- CSS
- Create React App

## Requirements

- Node.js and npm
- The [BugRepo backend](https://github.com/deepikarthinikanche/bugrepo-backend)
- PostgreSQL configured for the backend

## Setup

### 1. Clone the repository

```bash
git clone https://github.com/deepikarthinikanche/bugrepo-frontend.git
cd bugrepo-frontend
```

### 2. Install dependencies

```bash
npm install
```

### 3. Configure the backend URL

Create a `.env` file in the project root. You can start from the provided example:

```bash
cp .env.example .env
```

Set the API URL to the address where your backend is running:

```env
REACT_APP_API_URL=http://localhost:8080/api
```

The backend repository uses port `8080` by default. If you run it on another port or host, update this value accordingly.

### 4. Start the frontend

Make sure the backend and PostgreSQL database are running, then start the React application:

```bash
npm start
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## Application routes

| Route | Description |
|---|---|
| `/login` | Sign in |
| `/register` | Create an account |
| `/dashboard` | View bug reports and dashboard statistics |
| `/report` | Submit a bug report |
| `/bug/:id` | View and manage a bug report |
| `/my-bugs` | View bugs reported by you or assigned to you, depending on your role |

The dashboard, report, bug details, and My Bugs pages require authentication.

## Backend integration

The frontend communicates with the backend through the API URL configured in `REACT_APP_API_URL`.

The API service includes requests for:

- Authentication: register and login.
- Bug reports: list, create, view, update, assign, change status, and delete.
- User listing.
- Bug insights: retrieve, regenerate, and export reports.

The frontend stores the JWT returned by the backend in browser local storage and sends it as a Bearer token with API requests.

See the [backend README](https://github.com/deepikarthinikanche/bugrepo-backend/blob/main/README.md) for database configuration, API details, and backend startup instructions.

## Available scripts

```bash
npm start       # Start the development server
npm run build   # Create a production build
npm test        # Run tests
npm run eject   # Eject from Create React App
```

## License

This project is licensed under the ISC License.
