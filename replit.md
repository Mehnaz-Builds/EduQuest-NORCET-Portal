# AceNORCET - AIIMS Nursing Officer Exam Prep

## Overview

AceNORCET is a free web-based mock test platform designed to help nursing professionals prepare for the AIIMS Nursing Officer (NORCET) examination. The application provides practice quizzes covering nursing fundamentals and general knowledge/aptitude, simulating a real exam environment with timed tests, score tracking, and celebratory feedback for high performance.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Routing**: Wouter (lightweight client-side routing)
- **State Management**: TanStack React Query for server state, React useState for local state
- **Styling**: Tailwind CSS with shadcn/ui component library (New York style variant)
- **Animations**: Framer Motion for page transitions and micro-interactions
- **UI Components**: Radix UI primitives wrapped with shadcn/ui styling
- **Build Tool**: Vite with React plugin

### Backend Architecture
- **Runtime**: Node.js with Express
- **Language**: TypeScript (ESM modules)
- **API Pattern**: Simple REST endpoints defined in shared routes configuration
- **Development**: Vite middleware integration for HMR during development
- **Production**: Static file serving from built client assets

### Data Storage
- **Database Schema**: PostgreSQL with Drizzle ORM
- **Schema Definition**: Shared schema in `/shared/schema.ts` using Drizzle's pgTable
- **Current Implementation**: In-memory storage class (MemStorage) serving seeded question data
- **Client Storage**: LocalStorage for quiz results and high scores

### Project Structure
```
├── client/           # React frontend application
│   ├── src/
│   │   ├── components/   # Reusable UI components
│   │   ├── pages/        # Route page components
│   │   ├── hooks/        # Custom React hooks
│   │   └── lib/          # Utilities and query client
│   └── public/       # Static assets and PWA files
├── server/           # Express backend
│   ├── routes.ts     # API route definitions
│   ├── storage.ts    # Data storage abstraction
│   └── db.ts         # Database connection
├── shared/           # Shared types and schemas
│   ├── schema.ts     # Drizzle database schema
│   └── routes.ts     # API route type definitions
└── migrations/       # Drizzle database migrations
```

### Key Design Patterns
- **Shared Types**: Schema and route definitions shared between frontend and backend via `/shared` directory
- **Path Aliases**: `@/` for client source, `@shared/` for shared code
- **Type Safety**: Zod schemas for API response validation, Drizzle-Zod for database type inference
- **Progressive Enhancement**: Service worker and manifest for PWA capabilities

### Quiz System Design
- Three test modes: Nursing only (20 questions), GK only (20 questions), Full test (100 questions)
- Timed sessions with configurable duration per test type
- Questions shuffled randomly for each attempt
- Results stored in localStorage with high score tracking

## External Dependencies

### Database
- **PostgreSQL**: Primary database (configured via DATABASE_URL environment variable)
- **Drizzle ORM**: Type-safe database toolkit with PostgreSQL dialect
- **connect-pg-simple**: Session storage for Express (available but not currently active)

### Frontend Libraries
- **@tanstack/react-query**: Server state management and caching
- **framer-motion**: Animation library for smooth transitions
- **canvas-confetti**: Celebration effects for high scores
- **lucide-react**: Icon set
- **date-fns**: Date formatting utilities

### UI Framework
- **shadcn/ui**: Component library built on Radix UI primitives
- **Tailwind CSS**: Utility-first CSS framework
- **class-variance-authority**: Component variant management

### Development Tools
- **Vite**: Frontend build tool with HMR
- **esbuild**: Server bundling for production
- **tsx**: TypeScript execution for development
- **drizzle-kit**: Database migration and schema management

### PWA Support
- Service worker for offline caching
- Web app manifest for installability
- Configured for standalone display mode