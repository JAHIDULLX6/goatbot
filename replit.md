# SAGOR BOT V2 (GoatBot)

## Overview
A Facebook Messenger chat bot using a personal account, based on GoatBot V2 by NTKhang and updated by SaGor. Includes a web dashboard for bot management.

## Project Architecture
- **Language**: Node.js 20
- **Entry Point**: `index.js` - Starts an Express keep-alive server on port 5000 and spawns the main bot process (`SaGor.js`)
- **Bot Core**: `SaGor.js` - Main bot logic, loads config, sets up globals, initializes database, starts login
- **Dashboard**: `dashboard/app.js` - Express web dashboard on port 3001 for bot management
- **Database**: SQLite (configured in `config.json`)
- **Bot Scripts**: `scripts/cmds/` for commands, `scripts/events/` for event handlers

## Key Files
- `config.json` - Main bot configuration (Facebook account, database, dashboard settings)
- `configCommands.json` - Command configuration
- `account.txt` - Facebook login cookies/state
- `bot/login/login.js` - Facebook login handler
- `dashboard/` - Web dashboard (Express + Eta templates)

## Port Configuration
- Port 5000: Main HTTP server (keep-alive, exposed to web)
- Port 3001: Dashboard web interface (internal)

## Recent Changes
- 2026-02-06: Initial Replit setup
  - Configured index.js to use port 5000 bound to 0.0.0.0
  - Dashboard uses config-based port (3001) to avoid conflicts
  - Installed system dependencies for native modules (canvas, sqlite3, bcrypt)
  - Set up deployment config as VM (bot needs to stay running)
