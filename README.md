# Energy Lens

**Home Energy Monitoring System**

Energy Lens is a full-stack web application designed to help users monitor and manage household energy usage. The application provides a centralized dashboard for connected devices, displays simulated power consumption, and gives users tools to manage devices, set usage timers, and identify high-energy activity.

This project was developed as a Capstone II project with a focus on creating a simple, practical interface for understanding home electricity usage.

**[Live Demo](https://ihms-demo.onrender.com/)**

## Features

- Login and signup interface
- Central dashboard for household devices
- View active and total connected devices
- Monitor simulated real-time power usage
- Add and pair new household devices
- Edit and remove devices
- Set custom device timers
- High-energy usage alerts and notifications
- Device runtime tracking
- Settings and notification controls
- Persistent device data through PostgreSQL
- Local fallback data when the backend is unavailable
- Demo and simulation functionality for testing energy-related events

## Supported Devices

Energy Lens currently supports several common household device types, including:

- TVs
- Gaming consoles
- Washers and dryers
- Refrigerators
- Microwaves
- Ovens and stoves
- Lamps
- Computers
- Phone chargers
- Routers
- Fans

## Tech Stack

### Frontend

- React 19
- TypeScript
- Vite
- Tailwind CSS
- Radix UI
- Lucide React

### Backend

- Node.js
- Express
- PostgreSQL
- `pg`
- CORS
- dotenv

## Project Structure

```text
energy-lens/
├── client/                 # React + TypeScript frontend
│   ├── src/
│   │   ├── app/
│   │   │   ├── components/
│   │   │   ├── deviceApi.ts
│   │   │   ├── mockDatabase.ts
│   │   │   └── App.tsx
│   │   ├── styles/
│   │   └── main.tsx
│   └── package.json
│
├── server/                 # Node.js + Express backend
│   ├── index.js
│   └── package.json
│
└── README.md
```

## How It Works

The frontend provides the user interface for managing and monitoring household devices. Device information is requested from the Express REST API and stored in PostgreSQL.

When the server starts, it automatically creates the `devices` table if it does not already exist and seeds the database with sample household devices when the table is empty.

The application also maintains a local fallback so the interface can continue demonstrating device functionality if the API is temporarily unavailable.

## API Endpoints

| Method | Endpoint | Description |
| --- | --- | --- |
| `GET` | `/` | Checks backend and database connectivity |
| `GET` | `/api/devices` | Returns all devices |
| `POST` | `/api/devices` | Creates a new device |
| `PATCH` | `/api/devices/:id` | Updates an existing device |
| `DELETE` | `/api/devices/:id` | Removes a device |

## Getting Started

### Prerequisites

Make sure you have the following installed:

- Node.js
- npm
- PostgreSQL

### 1. Clone the Repository

```bash
git clone <your-repository-url>
cd <repository-folder>
```

### 2. Configure the Database

Create a PostgreSQL database for the project.

Inside the `server` directory, create a `.env` file:

```env
DATABASE_URL=postgresql://USERNAME:PASSWORD@localhost:5432/DATABASE_NAME
PORT=5000
```

Replace the values with your PostgreSQL credentials and database name.

### 3. Start the Backend

```bash
cd server
npm install
npm start
```

The backend runs on:

```text
http://localhost:5000
```

### 4. Start the Frontend

Open a second terminal:

```bash
cd client
npm install
npm run dev
```

Vite will display the local development URL in the terminal.

By default, the frontend connects to:

```text
http://localhost:5000
```

To use a different backend URL, create a `.env` file inside `client`:

```env
VITE_API_BASE_URL=http://localhost:5000
```

## Demo Behavior

Energy Lens currently uses simulated energy values rather than data from physical smart-home hardware. This allows the application to demonstrate realistic monitoring behavior, including:

- Devices turning on and off
- Changes in power consumption
- High-energy usage events
- Extended-runtime alerts
- Device timers
- Energy-related notifications

The device pairing interface is also simulated for demonstration purposes.

## Current Status

The core full-stack application is functional. The React frontend communicates with the Express API, while PostgreSQL stores device information and state.

Current development is focused on expanding the monitoring experience, improving data visualization, and building out additional energy insights.

## Future Improvements

- Historical energy usage charts
- Daily, weekly, monthly, and yearly usage views
- Household energy summaries and trends
- Energy-efficiency status indicators
- Real user authentication and authorization
- User-specific device storage
- Smart-plug or IoT hardware integration
- Estimated electricity cost calculations
- Dark mode and additional accessibility improvements

## Team

- Emre Akilli
- Juan Carlos Gomez
- Carlos Diaz
- David Palacio
- Henry Perez

## Purpose

Energy Lens was created to make household electricity consumption easier to understand. By presenting device activity and energy information through a straightforward dashboard, the project demonstrates how software can help users become more aware of where and how energy is being used in their homes.
