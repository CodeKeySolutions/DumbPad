# DumbPad

A stupid simple, no auth (unless you want it!), modern notepad application with auto-save functionality and dark mode support.

![image](https://github.com/user-attachments/assets/c6a00aac-f841-48a8-b8d3-c3d5378fc7d9)

## Table of Contents

## Features

- Simple, clean interface
- Auto-saving
- Dark mode support
- Responsive design
- Docker support
- Optional PIN protection
- File-based storage
- Data persistence across updates

## Quick Start

### Prerequisites

* Docker (recommended)
* Node.js >=20.0.0 (for local development)

### Option 1: Docker (For Dummies)

```bash
# Pull and run with one command
docker run -p 3000:3000 \
  -v ./data:/app/data \
  dumbwareio/dumbpad:latest
```

1. Go to http://localhost:3000
2. Start typing - Your notes auto-save
3. Marvel at how dumb easy this was

### Option 2: Docker Compose (For Dummies who like customizing)

Create a `docker-compose.yml` file:

```yaml
services:
  dumbpad:
    image: dumbwareio/dumbpad:latest
    ports:
      - 3000:3000
    volumes:
      # Where your notes will be stored
      - ./data:/app/data
    environment:
      # The title shown in the web interface
      SITE_TITLE: DumbPad
      # Optional PIN protection (leave empty to disable)
      DUMBPAD_PIN: 1234
      # The base URL for the application
      BASE_URL: http://localhost:3000
```

Then run:
```bash
docker compose up -d
```

1. Go to http://localhost:3000
2. Start typing - Your notes auto-save
3. Rejoice in the glory of your dumb notes

### Option 3: Running Locally (For Developers)

1. Install dependencies:
```bash
npm install
```

2. Set environment variables in `.env`:
```bash
PORT=3000                  # Port to run the server on
DUMBPAD_PIN=1234          # Optional PIN protection
SITE_TITLE=DumbPad        # Custom site title
BASE_URL=http://localhost:3000  # Base URL for the application
```

3. Start the server:
```bash
npm start
```

#### Windows Users

If you're using Windows PowerShell with Docker, use this format for paths:
```powershell
docker run -p 3000:3000 -v "${PWD}\data:/app/data" dumbwareio/dumbpad:latest
```

## Features

* 📝 Auto-saving notes
* 🌓 Dark/Light mode support
* 🔒 Optional PIN protection
* 📱 Mobile-friendly interface
* 🗂️ Multiple notepads
* ⬇️ Download notes as text files
* 🖨️ Print functionality
* 🔄 Real-time saving
* ⚡ Zero dependencies on client-side
* 🛡️ Built-in security features
* 🎨 Clean, modern interface
* 📦 Docker support with easy configuration

## Configuration

### Environment Variables

| Variable      | Description                                | Default               | Required |
|--------------|--------------------------------------------|-----------------------|----------|
| PORT         | Server port                                | 3000                  | No       |
| BASE_URL     | Base URL for the application              | http://localhost:PORT | No       |
| DUMBPAD_PIN  | PIN protection (4-10 digits)              | None                  | No       |
| SITE_TITLE   | Site title displayed in header            | DumbPad               | No       |

## Security

### Features

* Variable-length PIN support (4-10 digits)
* Constant-time PIN comparison
* Brute force protection:
  * 5 attempts maximum
  * 15-minute lockout after failed attempts
  * IP-based tracking
* Secure cookie handling
* No client-side PIN storage
* Rate limiting

## Technical Details

### Stack

* **Backend**: Node.js (>=20.0.0) with Express
* **Frontend**: Vanilla JavaScript (ES6+)
* **Container**: Docker with multi-stage builds
* **Security**: Express security middleware
* **Storage**: File-based with auto-save
* **Theme**: Dynamic dark/light mode with system preference support

### Dependencies

* express: Web framework
* cors: Cross-origin resource sharing
* dotenv: Environment configuration
* cookie-parser: Cookie handling
* express-rate-limit: Rate limiting

The `data` directory contains:
- `notepads.json`: List of all notepads
- Individual `.txt` files for each notepad's content

⚠️ Important: Never delete the `data` directory when updating! This is where all your notes are stored.

## Usage

- Just start typing! Your notes will be automatically saved.
- Use the theme toggle in the top-right corner to switch between light and dark mode.
- Press `Ctrl+S` (or `Cmd+S` on Mac) to force save.
- The save status will be shown at the bottom of the screen.
- If PIN protection is enabled, you'll need to enter the PIN to access the app.

## Technical Details

- Backend: Node.js with Express
- Frontend: Vanilla JavaScript
- Storage: File-based storage in `data` directory
- Styling: Modern CSS with CSS variables for theming
- Security: Constant-time PIN comparison, brute force protection

## Links

- GitHub: [github.com/dumbwareio/dumbpad](https://github.com/dumbwareio/dumbpad)
- Docker Hub: [hub.docker.com/r/dumbwareio/dumbpad](https://hub.docker.com/r/dumbwareio/dumbpad)

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes using conventional commits
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

See Development Guide for local setup and guidelines.

---

Made with ❤️ by DumbWare.io

## 🌐 Check Us Out
- **Website:** [dumbware.io](https://www.dumbware.io/)
- **Buy Us a Coffee:** [buymeacoffee.com/dumbware](https://buymeacoffee.com/dumbware) ☕
- **Join the Chaos:** [Discord](https://discord.gg/zJutzxWyq2) 💬

## Future Features

* Markdown support
* File attachments
* Collaborative editing

> Got an idea? Open an issue or submit a PR
