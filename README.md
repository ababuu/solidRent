# SolidRent

A comprehensive property management platform that streamlines the rental process for both property managers and tenants.

## 🏢 Project Overview

SolidRent is a full-stack web application designed to simplify property management operations. The platform enables:

- **Property Managers**: Manage properties, applications, leases, and tenant communications
- **Tenants**: Browse properties, submit applications, manage leases, and pay rent

## 🛠 Tech Stack

### Frontend

- **Framework**: Next.js 14+ with TypeScript
- **Styling**: Tailwind CSS
- **State Management**: Redux
- **UI Components**: Shadcn/ui
- **Form Management**: React Hook Form
- **HTTP Client**: Axios

### Backend

- **Runtime**: Node.js
- **Framework**: Express.js
- **Language**: TypeScript
- **Database**: PostgreSQL (via Prisma ORM)
- **Database Tool**: Prisma ORM
- **Authentication**: Custom middleware (authMiddleware)

### DevOps

- **Containerization**: Docker & Docker Compose
- **Process Manager**: PM2 (for production deployment)

## 📁 Project Structure

```
solidRent/
├── docker-compose.yml          # Docker compose configuration for local development
├── client/                      # Next.js frontend application
│   ├── src/
│   │   ├── app/               # App router and pages
│   │   ├── components/        # Reusable React components
│   │   ├── hooks/             # Custom React hooks
│   │   ├── lib/               # Utilities, schemas, constants
│   │   ├── state/             # Redux state management
│   │   └── types/             # TypeScript type definitions
│   ├── public/                # Static assets
│   └── package.json           # Frontend dependencies
│
└── server/                      # Node.js/Express backend application
    ├── src/
    │   ├── index.ts           # Server entry point
    │   ├── controllers/       # Request handlers
    │   ├── middleware/        # Express middleware
    │   └── routes/            # API route definitions
    ├── prisma/
    │   ├── schema.prisma      # Database schema
    │   ├── migrations/        # Database migrations
    │   └── seedData/          # Sample data for seeding
    └── package.json           # Backend dependencies
```

## 🚀 Getting Started

### Prerequisites

- Node.js 18+ and npm/yarn
- Docker and Docker Compose (for containerized setup)
- PostgreSQL 13+ (if running without Docker)

### Installation

1. **Clone the repository**

   ```bash
   git clone <repository-url>
   cd solidRent
   ```

2. **Using Docker Compose (Recommended)**

   ```bash
   docker-compose up
   ```

   This will start both the frontend and backend services with all dependencies.

3. **Manual Setup**

   **Backend:**

   ```bash
   cd server
   npm install

   # Set up environment variables
   cp .env.example .env

   # Run database migrations
   npx prisma migrate dev

   # (Optional) Seed the database
   npx prisma db seed

   # Start the server
   npm run dev
   ```

   **Frontend:**

   ```bash
   cd client
   npm install

   # Set up environment variables
   cp .env.example .env.local

   # Start the development server
   npm run dev
   ```

## 📝 Environment Variables

Create `.env` files in both `client/` and `server/` directories with the necessary configuration:

**Backend (.env):**

```
DATABASE_URL=postgresql://user:password@localhost:5432/solidrent
PORT=3001
NODE_ENV=development
```

**Frontend (.env.local):**

```
NEXT_PUBLIC_API_URL=http://localhost:3001
```

## 🧪 Running the Application

### Development Mode

```bash
# Backend
cd server && npm run dev

# Frontend (in another terminal)
cd client && npm run dev
```

### Production Build

```bash
# Backend
cd server && npm run build && npm run start

# Frontend
cd client && npm run build && npm start
```

## 🗄 Database Management

### Migrations

```bash
cd server

# Create a new migration
npx prisma migrate dev --name migration_name

# View database in Prisma Studio
npx prisma studio
```

### Seeding

```bash
cd server
npx prisma db seed
```

## 📚 API Routes

The backend provides the following route groups:

- `/api/managers` - Manager-related endpoints
- `/api/properties` - Property management endpoints
- `/api/tenants` - Tenant-related endpoints
- `/api/applications` - Rental application endpoints
- `/api/leases` - Lease management endpoints

## 🔐 Authentication

The application uses custom authentication middleware. All protected routes require authentication via the `authMiddleware`.

## 🚀 Deployment

### AWS EC2 Deployment

See [server/aws-ec2-instructions.md](server/aws-ec2-instructions.md) for detailed deployment instructions.

### PM2 Process Manager

The backend uses PM2 for process management. Configuration is defined in `server/ecosystem.config.js`.

## 🤝 Contributing

1. Create a feature branch (`git checkout -b feature/amazing-feature`)
2. Commit your changes (`git commit -m 'Add amazing feature'`)
3. Push to the branch (`git push origin feature/amazing-feature`)
4. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 💬 Support

For issues or questions, please open an issue on the repository or contact the development team.

---

**Last Updated**: May 2026
