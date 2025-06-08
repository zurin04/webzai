# Crypto Airdrop Platform

A comprehensive crypto learning and engagement platform featuring user management, airdrop listings, real-time chat, and role-based access controls.

## Features

- **User Authentication** - Registration, login, Web3 wallet integration
- **Airdrop Management** - Create, view, and manage crypto airdrop tutorials
- **Real-time Chat** - WebSocket-powered community discussions
- **Crypto Tracker** - Live cryptocurrency price feeds
- **Admin Dashboard** - User management and content moderation
- **Creator System** - Application process for content creators
- **Newsletter** - Email subscription management
- **Mobile Responsive** - Optimized for all devices

## Tech Stack

- **Frontend:** React, TypeScript, Tailwind CSS, shadcn/ui
- **Backend:** Node.js, Express, TypeScript
- **Database:** PostgreSQL with Drizzle ORM
- **Real-time:** WebSockets for chat
- **Authentication:** Session-based + Web3 wallet support
- **Process Management:** PM2
- **Reverse Proxy:** Nginx

## Quick Deploy

### Automated Installation (Recommended)

**For Root Users:**
```bash
wget https://raw.githubusercontent.com/your-username/crypto-airdrop-platform/main/root-deploy.sh
chmod +x root-deploy.sh
./root-deploy.sh
```

**For Non-Root Users:**
```bash
wget https://raw.githubusercontent.com/your-username/crypto-airdrop-platform/main/vps-auto-setup.sh
chmod +x vps-auto-setup.sh
./vps-auto-setup.sh
```

Setup time: 5-10 minutes | No manual configuration required

### Manual Installation

For detailed step-by-step instructions, see [VPS_DEPLOYMENT_GUIDE.md](VPS_DEPLOYMENT_GUIDE.md)

## Development

### Prerequisites
- Node.js 20+
- PostgreSQL
- Git

### Local Setup
```bash
# Clone repository
git clone https://github.com/your-username/crypto-airdrop-platform.git
cd crypto-airdrop-platform

# Install dependencies
npm install

# Setup database
npm run db:push
npm run db:seed

# Start development server
npm run dev
```

The application will be available at `http://localhost:5000`

### Default Credentials
- **Admin:** `admin` / `admin123`
- **Demo:** `demo` / `demo123`

## Production Deployment

### Requirements
- Ubuntu 20.04+ or Debian 11+ VPS
- 1GB+ RAM, 20GB+ storage
- Domain name (optional but recommended)

### Environment Variables
```env
NODE_ENV=production
DATABASE_URL=postgresql://user:password@localhost:5432/database
SESSION_SECRET=your_secure_session_secret
PORT=5000
```

### Management Commands
```bash
# Application status
pm2 status

# View logs
pm2 logs crypto-airdrop-platform

# Restart application
pm2 restart crypto-airdrop-platform

# Update application
/opt/crypto-airdrop/scripts/update.sh

# Database backup
/opt/crypto-airdrop/scripts/backup.sh
```

## Security Features

- SSL/TLS encryption
- Firewall protection
- Security headers
- Password hashing
- Session management
- Input validation
- SQL injection prevention
- XSS protection

## API Endpoints

### Authentication
- `POST /api/register` - User registration
- `POST /api/login` - User login
- `POST /api/logout` - User logout
- `GET /api/user` - Get current user

### Airdrops
- `GET /api/airdrops` - List airdrops
- `GET /api/airdrops/featured` - Featured airdrops
- `GET /api/airdrop/:id` - Get airdrop details
- `POST /api/airdrops` - Create airdrop (admin/creator)

### Categories
- `GET /api/categories` - List categories
- `POST /api/categories` - Create category (admin)

### Crypto
- `GET /api/crypto/prices` - Live crypto prices

### Chat
- `WebSocket /ws` - Real-time chat

## VPS Deployment

This project is ready for production deployment on Ubuntu/Debian VPS servers.

### Quick Setup
1. Follow the complete step-by-step guide in [VPS_DEPLOYMENT_GUIDE.md](VPS_DEPLOYMENT_GUIDE.md)
2. Configure your environment variables using `.env.example` as a template
3. Use the included `ecosystem.config.js` for PM2 process management

### Default Credentials
After deployment, login with:
- **Admin:** `admin` / `admin123`
- **Demo User:** `demo` / `demo123`

**Important:** Change these passwords immediately after first login.

### Requirements
- Node.js 20+
- PostgreSQL 12+
- Nginx (recommended)
- PM2 for process management

## Development

```bash
# Install dependencies
npm install

# Setup database
npm run db:push
npm run db:seed

# Start development server
npm run dev
```

## License

MIT License - see LICENSE file for details

## Support

For deployment issues, check the troubleshooting section in [VPS_DEPLOYMENT_GUIDE.md](VPS_DEPLOYMENT_GUIDE.md)