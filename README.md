# AI Podcast Generator

A React application that allows users to generate podcasts by speaking a topic. This application uses the Web Speech API for voice recognition and integrates with a backend service to generate audio podcasts.

## Issue Fixed

The original `server.js` file contained React JSX code instead of a Node.js server implementation. This caused the error:
```
Uncaught SyntaxError SyntaxError: Unexpected token '<'
```

This error occurred because Node.js cannot parse JSX syntax directly. The file has been restructured with a proper Node.js server and the React component has been moved to its own file.

## Project Structure

- `server.js` - The Node.js server using Express
- `App.jsx` - The main React component
- `public/index.html` - The HTML entry point
- `package.json` - Project dependencies and scripts

## Prerequisites

- Node.js (version 14 or higher)
- npm (comes with Node.js)

## Installation

1. Install the required dependencies:
```bash
npm install
```

## Running the Application

1. Start the server:
```bash
npm start
```

2. Open your browser and navigate to:
```
http://localhost:3000
```

## Development

For development with auto-restart on file changes:
```bash
npm run dev
```

## How It Works

1. The Express server serves the React application from the `public` directory
2. The React component uses the Web Speech API to capture voice input
3. When a topic is spoken, it's sent to a backend service to generate a podcast
4. The generated podcast is then played back in the browser

## Firebase Configuration

Before deploying, replace the Firebase configuration in `App.jsx` with your actual Firebase project credentials.

## Backend Integration

The application expects a backend service at `http://localhost:5000` with a `/generate-podcast` endpoint. You'll need to implement this service separately or update the URL in `App.jsx` to point to your actual backend.
