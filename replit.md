# LeNoobInconnu STUDIO - Creator Tools Dashboard

## Overview

LeNoobInconnu STUDIO is a web application that provides a suite of tools designed for beginner YouTube creators. The platform features a tools dashboard where users can discover and access various utilities to help grow their YouTube channels, including thumbnail generators, analytics dashboards, video planners, and title optimizers.

The application is built as a full-stack TypeScript project with a React frontend and Express backend, featuring a dark purple theme inspired by modern dashboard interfaces.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture

**Framework**: React 18 with TypeScript
- **Routing**: wouter for client-side navigation
- **UI Components**: shadcn/ui component library with Radix UI primitives
- **Styling**: Tailwind CSS with custom dark theme configuration
- **State Management**: TanStack Query (React Query) for server state
- **Form Handling**: React Hook Form with Zod validation

**Design System**:
- Custom dark purple theme (`#5b5ff5` primary color)
- Color palette includes background-dark (`#1e1e2f`), card backgrounds, and status colors
- Typography using Segoe UI font stack
- Responsive design with mobile-first approach
- Component variants using class-variance-authority

**Key Pages**:
- Home page: Landing page with project introduction
- Tools page: Grid layout displaying available tools with status badges
- 404 page: Error handling for undefined routes

### Backend Architecture

**Framework**: Express.js with TypeScript
- **Runtime**: Node.js with ES modules
- **Build Tool**: Vite for frontend bundling, esbuild for backend
- **Development**: tsx for TypeScript execution in development

**API Structure**:
- RESTful API endpoints under `/api` prefix
- Tool management: GET all tools, GET by ID, POST create, PATCH update, DELETE
- JSON request/response format
- Request logging middleware for API calls

**Data Layer**:
- In-memory storage implementation (`MemStorage`) for development
- Interface-based storage abstraction (`IStorage`) for future database integration
- Seeded data for default tools

### Database Design

**ORM**: Drizzle ORM configured for PostgreSQL
- Schema definition in TypeScript with Drizzle
- Zod integration for runtime validation
- Migration support via drizzle-kit

**Schema**:
- `users` table: id (UUID), username (unique), password
- `tools` table: id (UUID), name, description, icon (Font Awesome class), status (enum: available/development/maintenance)

**Note**: Currently using in-memory storage; PostgreSQL integration is configured but not yet implemented.

### Authentication & Authorization

No authentication system is currently implemented. The user schema exists in the database definition but is not actively used in the application.

### Design Pattern Decisions

**Component-Based Architecture**:
- Reusable UI components from shadcn/ui
- Custom components: `Navbar`, `ToolCard`
- Separation of concerns between presentation and business logic

**Type Safety**:
- Shared schema definitions between frontend and backend
- Zod schemas for runtime validation
- TypeScript strict mode enabled

**State Management Strategy**:
- Server state managed by React Query with aggressive caching (`staleTime: Infinity`)
- No refetch on window focus to reduce server load
- Query keys following REST endpoint structure

**Styling Approach**:
- Reference-based design continuing from provided HTML template
- Utility-first CSS with Tailwind
- CSS custom properties for theming
- Hover and active state elevations for interactive feedback

## External Dependencies

### Third-Party UI Libraries
- **Radix UI**: Headless component primitives (accordion, dialog, dropdown, etc.)
- **shadcn/ui**: Pre-built accessible component library
- **Font Awesome 6.5.2**: Icon library (CDN)
- **Lucide React**: Additional icon components

### Data & State Management
- **TanStack Query v5**: Server state synchronization and caching
- **React Hook Form**: Form state and validation
- **Zod**: Schema validation and type inference
- **Drizzle Zod**: Integration between Drizzle ORM and Zod

### Database & ORM
- **Drizzle ORM**: TypeScript ORM for SQL databases
- **@neondatabase/serverless**: PostgreSQL serverless driver
- **connect-pg-simple**: PostgreSQL session store (configured but not used)

### Utilities
- **wouter**: Lightweight routing library
- **clsx & tailwind-merge**: Class name utilities
- **class-variance-authority**: Component variant management
- **date-fns**: Date manipulation library
- **nanoid**: Unique ID generation

### Development Tools
- **Vite**: Frontend build tool and dev server
- **Replit plugins**: Development banner, error overlay, cartographer
- **tsx**: TypeScript execution for Node.js
- **esbuild**: Backend bundling

### CSS & Styling
- **Tailwind CSS**: Utility-first CSS framework
- **PostCSS**: CSS processing
- **Autoprefixer**: CSS vendor prefixing