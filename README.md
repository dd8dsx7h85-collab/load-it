# Advanced App Demo - Production Ready

A full-stack production-ready application with YouTube search, camera/microphone access, and user data storage.

## Features

- **YouTube Search**: Search and display YouTube videos using the YouTube API
- **Camera & Microphone**: Access device camera and microphone with recording capabilities
- **User Settings**: Save user preferences to MongoDB database
- **Production Ready**: Optimized build, error handling, and deployment configuration

## Quick Start

### Development

1. **Install dependencies:**
   ```bash
   # Install client dependencies
   npm install
   
   # Install server dependencies
   cd server
   npm install
   cd ..
   ```

2. **Configure environment variables:**
   
   Edit `server/.env`:
   ```env
   PORT=4000
   MONGODB_URI=your_mongodb_connection_string
   YOUTUBE_API_KEY=YOUR_YOUTUBE_API_KEY
   ```

3. **Start development servers:**
   
   Terminal 1 (Server):
   ```bash
   cd server
   npm start
   ```
   
   Terminal 2 (Client):
   ```bash
   npm run dev
   ```

4. **Open in browser:**
   - Client: http://localhost:5173
   - Server API: http://localhost:4000

## Production Build

### Build for Production

```bash
# Build the frontend
npm run build

# This creates an optimized build in the 'dist' folder
```

### Run Production Server

```bash
# Set NODE_ENV=production and start server
npm run start:prod

# Or manually:
cd server
NODE_ENV=production npm start
```

The production server will:
- Serve the optimized React app from `dist/`
- Handle API requests at `/api/*`
- Serve the React app for all other routes (SPA routing)

## Project Structure

```
loopd/
├── server/              # Express backend
│   ├── index.js        # Server entry point
│   ├── .env            # Server environment variables
│   └── package.json    # Server dependencies
├── src/                # React frontend source
│   ├── App.jsx
│   ├── YouTubeSearch.jsx
│   ├── CameraMic.jsx
│   ├── UserSettings.jsx
│   └── main.jsx
├── dist/               # Production build (generated)
├── .env                # Client environment variables
├── .env.production     # Production environment variables
├── vite.config.js      # Vite configuration
├── package.json        # Client dependencies
└── DEPLOY.md           # Detailed deployment guide
```

## Environment Variables

### Development (.env)
```env
VITE_API_BASE=http://localhost:4000
```

### Production (.env.production)
```env
VITE_API_BASE=/api
```

### Server (server/.env)
```env
NODE_ENV=production
PORT=4000
MONGODB_URI=your_mongodb_connection_string
YOUTUBE_API_KEY=YOUR_YOUTUBE_API_KEY
```

## Getting API Keys

### YouTube Data API Key
1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project or select existing
3. Enable "YouTube Data API v3"
4. Create credentials (API Key)
5. Copy key to `server/.env`

### MongoDB Connection String
1. Sign up at [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) (free tier available)
2. Create a cluster
3. Get connection string
4. Replace `<password>` with your database password
5. Add to `server/.env` as `MONGODB_URI`

## Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run build:prod` - Build with production mode
- `npm run preview` - Preview production build locally
- `npm start` - Start server (development)
- `npm run start:prod` - Start server (production)

## Deployment

See [DEPLOY.md](./DEPLOY.md) for detailed deployment instructions including:
- Single server deployment
- Separate frontend/backend deployment
- Docker deployment
- Platform-specific guides (Heroku, Vercel, Railway, etc.)

## Tech Stack

- **Frontend**: React 18, Vite, Axios
- **Backend**: Express.js, MongoDB (Mongoose)
- **APIs**: YouTube Data API v3
- **Build**: Vite (optimized production builds)

## License

MIT
