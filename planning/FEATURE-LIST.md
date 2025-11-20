# HOTO Delivery Platform - Comprehensive Feature List

**Version:** 1.0
**Date:** November 20, 2025
**Status:** Feature Specification Phase
**Target Delivery:** January 23, 2026

---

## Table of Contents
1. [File System Structure](#file-system-structure)
2. [Shared Infrastructure](#shared-infrastructure)
3. [Feature 1: Dashboard Module](#feature-1-dashboard-module)
4. [Feature 2: HOTO Manager Module](#feature-2-hoto-manager-module)
5. [Feature 3: RFI Manager Module](#feature-3-rfi-manager-module)
6. [Feature 4: Scheduling Manager Module](#feature-4-scheduling-manager-module)
7. [Feature 5: CAD Manager Module](#feature-5-cad-manager-module)
8. [Cross-Cutting Concerns](#cross-cutting-concerns)

---

## File System Structure

### Frontend Repository Structure
```
hoto-platform-frontend/
├── public/
│   ├── assets/
│   │   ├── icons/
│   │   ├── images/
│   │   └── fonts/
│   └── index.html
│
├── src/
│   ├── app/
│   │   ├── App.tsx
│   │   ├── App.css
│   │   ├── store.ts              # Redux store configuration
│   │   └── rootReducer.ts        # Root reducer combining all slices
│   │
│   ├── components/
│   │   ├── common/
│   │   │   ├── Button/
│   │   │   │   ├── Button.tsx
│   │   │   │   ├── Button.module.css
│   │   │   │   └── Button.test.tsx
│   │   │   ├── Input/
│   │   │   ├── Select/
│   │   │   ├── Table/
│   │   │   ├── Modal/
│   │   │   ├── Toast/
│   │   │   ├── Loader/
│   │   │   ├── Card/
│   │   │   ├── Tabs/
│   │   │   ├── Dropdown/
│   │   │   └── DatePicker/
│   │   │
│   │   ├── layout/
│   │   │   ├── Header/
│   │   │   ├── Sidebar/
│   │   │   ├── Footer/
│   │   │   └── MainLayout/
│   │   │
│   │   └── charts/
│   │       ├── BarChart/
│   │       ├── PieChart/
│   │       ├── LineChart/
│   │       ├── GanttChart/
│   │       └── ProgressChart/
│   │
│   ├── features/
│   │   ├── auth/
│   │   │   ├── components/
│   │   │   │   ├── LoginForm/
│   │   │   │   ├── RegisterForm/
│   │   │   │   └── PasswordReset/
│   │   │   ├── hooks/
│   │   │   │   └── useAuth.ts
│   │   │   ├── services/
│   │   │   │   └── authService.ts
│   │   │   ├── slices/
│   │   │   │   └── authSlice.ts
│   │   │   └── types/
│   │   │       └── auth.types.ts
│   │   │
│   │   ├── dashboard/
│   │   │   ├── components/
│   │   │   │   ├── DashboardLayout/
│   │   │   │   ├── OMMDeliveryChart/
│   │   │   │   ├── GDLDeliveryChart/
│   │   │   │   ├── OverallProgressChart/
│   │   │   │   ├── FilterPanel/
│   │   │   │   └── StatisticsCards/
│   │   │   ├── hooks/
│   │   │   │   └── useDashboardData.ts
│   │   │   ├── services/
│   │   │   │   └── dashboardService.ts
│   │   │   ├── slices/
│   │   │   │   └── dashboardSlice.ts
│   │   │   ├── types/
│   │   │   │   └── dashboard.types.ts
│   │   │   └── pages/
│   │   │       └── DashboardPage.tsx
│   │   │
│   │   ├── hoto-manager/
│   │   │   ├── components/
│   │   │   │   ├── ChecklistTable/
│   │   │   │   ├── ChecklistEditor/
│   │   │   │   ├── DCPItemTracker/
│   │   │   │   ├── ProgressIndicator/
│   │   │   │   ├── AssignmentPanel/
│   │   │   │   └── ChecklistFilters/
│   │   │   ├── hooks/
│   │   │   │   ├── useChecklist.ts
│   │   │   │   └── useDCPItems.ts
│   │   │   ├── services/
│   │   │   │   └── hotoService.ts
│   │   │   ├── slices/
│   │   │   │   └── hotoSlice.ts
│   │   │   ├── types/
│   │   │   │   └── hoto.types.ts
│   │   │   └── pages/
│   │   │       ├── ChecklistListPage.tsx
│   │   │       └── ChecklistDetailPage.tsx
│   │   │
│   │   ├── rfi-manager/
│   │   │   ├── components/
│   │   │   │   ├── RFIForm/
│   │   │   │   ├── RFITable/
│   │   │   │   ├── RFIDetail/
│   │   │   │   ├── ResponseThread/
│   │   │   │   ├── AttachmentUploader/
│   │   │   │   └── ExportControls/
│   │   │   ├── hooks/
│   │   │   │   └── useRFI.ts
│   │   │   ├── services/
│   │   │   │   └── rfiService.ts
│   │   │   ├── slices/
│   │   │   │   └── rfiSlice.ts
│   │   │   ├── types/
│   │   │   │   └── rfi.types.ts
│   │   │   └── pages/
│   │   │       ├── RFIListPage.tsx
│   │   │       └── RFIDetailPage.tsx
│   │   │
│   │   ├── scheduling/
│   │   │   ├── components/
│   │   │   │   ├── MPPUploader/
│   │   │   │   ├── TimelineViewer/
│   │   │   │   ├── MilestoneTracker/
│   │   │   │   ├── TaskTable/
│   │   │   │   └── ScheduleFilters/
│   │   │   ├── hooks/
│   │   │   │   └── useSchedule.ts
│   │   │   ├── services/
│   │   │   │   └── schedulingService.ts
│   │   │   ├── slices/
│   │   │   │   └── schedulingSlice.ts
│   │   │   ├── types/
│   │   │   │   └── scheduling.types.ts
│   │   │   └── pages/
│   │   │       └── SchedulingPage.tsx
│   │   │
│   │   └── cad-manager/
│   │       ├── components/
│   │       │   ├── DrawingViewer/
│   │       │   ├── AnnotationToolbar/
│   │       │   ├── LayerPanel/
│   │       │   ├── ChatInterface/
│   │       │   ├── VersionHistory/
│   │       │   └── ExportDialog/
│   │       ├── hooks/
│   │       │   ├── useDrawing.ts
│   │       │   └── useAnnotations.ts
│   │       ├── services/
│   │       │   └── cadService.ts
│   │       ├── slices/
│   │       │   └── cadSlice.ts
│   │       ├── types/
│   │       │   └── cad.types.ts
│   │       └── pages/
│   │           └── CADManagerPage.tsx
│   │
│   ├── services/
│   │   ├── api/
│   │   │   ├── axiosConfig.ts
│   │   │   ├── endpoints.ts
│   │   │   └── interceptors.ts
│   │   ├── storage/
│   │   │   └── localStorage.ts
│   │   └── notifications/
│   │       └── notificationService.ts
│   │
│   ├── hooks/
│   │   ├── useDebounce.ts
│   │   ├── useMediaQuery.ts
│   │   └── usePermissions.ts
│   │
│   ├── utils/
│   │   ├── validators/
│   │   │   └── formValidators.ts
│   │   ├── formatters/
│   │   │   ├── dateFormatter.ts
│   │   │   └── numberFormatter.ts
│   │   ├── helpers/
│   │   │   └── dataHelpers.ts
│   │   └── constants/
│   │       ├── apiConstants.ts
│   │       └── appConstants.ts
│   │
│   ├── styles/
│   │   ├── variables.css
│   │   ├── global.css
│   │   ├── reset.css
│   │   └── themes/
│   │       └── default.css
│   │
│   ├── types/
│   │   ├── global.d.ts
│   │   └── api.types.ts
│   │
│   ├── routes/
│   │   ├── AppRoutes.tsx
│   │   ├── PrivateRoute.tsx
│   │   └── routeConfig.ts
│   │
│   └── main.tsx
│
├── tests/
│   ├── integration/
│   ├── e2e/
│   └── utils/
│
├── .env.example
├── .env.development
├── .env.production
├── package.json
├── tsconfig.json
├── vite.config.ts
├── .eslintrc.js
├── .prettierrc
└── README.md
```

### Backend Repository Structure
```
hoto-platform-backend/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/
│   │   │       └── hoto/
│   │   │           ├── HotoApplication.java
│   │   │           │
│   │   │           ├── config/
│   │   │           │   ├── SecurityConfig.java
│   │   │           │   ├── CosmosDBConfig.java
│   │   │           │   ├── FirebaseConfig.java
│   │   │           │   ├── AzureCommsConfig.java
│   │   │           │   └── CorsConfig.java
│   │   │           │
│   │   │           ├── controllers/
│   │   │           │   ├── AuthController.java
│   │   │           │   ├── DashboardController.java
│   │   │           │   ├── HotoController.java
│   │   │           │   ├── RFIController.java
│   │   │           │   ├── SchedulingController.java
│   │   │           │   └── CADController.java
│   │   │           │
│   │   │           ├── services/
│   │   │           │   ├── auth/
│   │   │           │   │   ├── AuthService.java
│   │   │           │   │   ├── UserService.java
│   │   │           │   │   └── PermissionService.java
│   │   │           │   ├── dashboard/
│   │   │           │   │   └── DashboardService.java
│   │   │           │   ├── hoto/
│   │   │           │   │   ├── ChecklistService.java
│   │   │           │   │   └── DCPService.java
│   │   │           │   ├── rfi/
│   │   │           │   │   ├── RFIService.java
│   │   │           │   │   └── EmailNotificationService.java
│   │   │           │   ├── scheduling/
│   │   │           │   │   ├── SchedulingService.java
│   │   │           │   │   └── MPPParserService.java
│   │   │           │   ├── cad/
│   │   │           │   │   ├── CADService.java
│   │   │           │   │   ├── DrawingService.java
│   │   │           │   │   ├── AnnotationService.java
│   │   │           │   │   └── ChatService.java
│   │   │           │   └── common/
│   │   │           │       ├── FileStorageService.java
│   │   │           │       └── ExportService.java
│   │   │           │
│   │   │           ├── repositories/
│   │   │           │   ├── UserRepository.java
│   │   │           │   ├── ChecklistRepository.java
│   │   │           │   ├── DCPItemRepository.java
│   │   │           │   ├── RFIRepository.java
│   │   │           │   ├── ScheduleRepository.java
│   │   │           │   ├── DrawingRepository.java
│   │   │           │   └── AnnotationRepository.java
│   │   │           │
│   │   │           ├── models/
│   │   │           │   ├── entities/
│   │   │           │   │   ├── User.java
│   │   │           │   │   ├── Checklist.java
│   │   │           │   │   ├── ChecklistItem.java
│   │   │           │   │   ├── DCPItem.java
│   │   │           │   │   ├── RFI.java
│   │   │           │   │   ├── RFIResponse.java
│   │   │           │   │   ├── Schedule.java
│   │   │           │   │   ├── ScheduleTask.java
│   │   │           │   │   ├── Drawing.java
│   │   │           │   │   ├── Annotation.java
│   │   │           │   │   └── ChatMessage.java
│   │   │           │   │
│   │   │           │   ├── dto/
│   │   │           │   │   ├── requests/
│   │   │           │   │   │   ├── LoginRequest.java
│   │   │           │   │   │   ├── CreateChecklistRequest.java
│   │   │           │   │   │   ├── CreateRFIRequest.java
│   │   │           │   │   │   └── UploadDrawingRequest.java
│   │   │           │   │   └── responses/
│   │   │           │   │       ├── LoginResponse.java
│   │   │           │   │       ├── DashboardResponse.java
│   │   │           │   │       ├── ChecklistResponse.java
│   │   │           │   │       └── RFIResponse.java
│   │   │           │   │
│   │   │           │   └── enums/
│   │   │           │       ├── UserRole.java
│   │   │           │       ├── ChecklistStatus.java
│   │   │           │       ├── RFIStatus.java
│   │   │           │       └── AnnotationType.java
│   │   │           │
│   │   │           ├── security/
│   │   │           │   ├── JwtTokenProvider.java
│   │   │           │   ├── JwtAuthenticationFilter.java
│   │   │           │   └── CustomUserDetailsService.java
│   │   │           │
│   │   │           ├── exceptions/
│   │   │           │   ├── GlobalExceptionHandler.java
│   │   │           │   ├── ResourceNotFoundException.java
│   │   │           │   ├── UnauthorizedException.java
│   │   │           │   └── ValidationException.java
│   │   │           │
│   │   │           ├── validators/
│   │   │           │   ├── ChecklistValidator.java
│   │   │           │   ├── RFIValidator.java
│   │   │           │   └── FileValidator.java
│   │   │           │
│   │   │           └── utils/
│   │   │               ├── DateUtils.java
│   │   │               ├── FileUtils.java
│   │   │               └── PDFUtils.java
│   │   │
│   │   └── resources/
│   │       ├── application.properties
│   │       ├── application-dev.properties
│   │       ├── application-prod.properties
│   │       └── templates/
│   │           └── email/
│   │               ├── rfi-notification.html
│   │               └── rfi-response.html
│   │
│   └── test/
│       └── java/
│           └── com/
│               └── hoto/
│                   ├── controllers/
│                   ├── services/
│                   └── integration/
│
├── pom.xml
├── Dockerfile
├── .gitignore
└── README.md
```

---

## Shared Infrastructure

### Technology Stack
- **Frontend:** React 18.2, TypeScript 5.0, Vite 4.0
- **State Management:** Redux Toolkit 1.9
- **Backend:** Java 17, Spring Boot 3.1
- **Database:** Azure Cosmos DB (SQL API)
- **Authentication:** Firebase Authentication
- **Email:** Azure Communications Services
- **File Storage:** Azure Blob Storage
- **Hosting:** Azure App Service (Australian Region)
- **CI/CD:** Azure DevOps Pipelines

### Design System Foundation

#### Color Palette
```css
/* Primary Colors */
--primary-blue: #2E5090;        /* Main brand color */
--primary-blue-dark: #1F3A66;   /* Hover states */
--primary-blue-light: #4A6FA8;  /* Disabled states */

/* Secondary Colors */
--secondary-gray: #5A6872;      /* Text and icons */
--secondary-gray-light: #E8EAED; /* Borders and dividers */
--secondary-gray-dark: #2D3539;  /* Headers */

/* Status Colors */
--status-success: #28A745;      /* Completed, Success */
--status-warning: #FFC107;      /* In Progress, Warning */
--status-danger: #DC3545;       /* Overdue, Error */
--status-info: #17A2B8;         /* Info, Pending */

/* Background Colors */
--bg-primary: #FFFFFF;          /* Main background */
--bg-secondary: #F5F6F8;        /* Secondary background */
--bg-tertiary: #E8EAED;         /* Tertiary background */

/* Text Colors */
--text-primary: #212529;        /* Primary text */
--text-secondary: #5A6872;      /* Secondary text */
--text-muted: #9BA3AB;          /* Muted text */
--text-inverse: #FFFFFF;        /* Text on dark backgrounds */
```

#### Typography
```css
/* Font Family */
--font-primary: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
--font-monospace: 'Courier New', Courier, monospace;

/* Font Sizes */
--font-size-xs: 0.75rem;    /* 12px */
--font-size-sm: 0.875rem;   /* 14px */
--font-size-base: 1rem;     /* 16px */
--font-size-lg: 1.125rem;   /* 18px */
--font-size-xl: 1.25rem;    /* 20px */
--font-size-2xl: 1.5rem;    /* 24px */
--font-size-3xl: 2rem;      /* 32px */

/* Font Weights */
--font-weight-normal: 400;
--font-weight-medium: 500;
--font-weight-semibold: 600;
--font-weight-bold: 700;

/* Line Heights */
--line-height-tight: 1.2;
--line-height-normal: 1.5;
--line-height-relaxed: 1.8;
```

#### Spacing System
```css
--spacing-xs: 0.25rem;   /* 4px */
--spacing-sm: 0.5rem;    /* 8px */
--spacing-md: 1rem;      /* 16px */
--spacing-lg: 1.5rem;    /* 24px */
--spacing-xl: 2rem;      /* 32px */
--spacing-2xl: 3rem;     /* 48px */
--spacing-3xl: 4rem;     /* 64px */
```

#### Border Radius
```css
--radius-sm: 2px;
--radius-md: 4px;
--radius-lg: 6px;
--radius-xl: 8px;
--radius-round: 50%;
```

#### Shadows
```css
--shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.05);
--shadow-md: 0 2px 4px rgba(0, 0, 0, 0.1);
--shadow-lg: 0 4px 8px rgba(0, 0, 0, 0.15);
--shadow-xl: 0 8px 16px rgba(0, 0, 0, 0.2);
```

---

## Feature 1: Dashboard Module

### Feature Goal
Provide executives, project managers, and stakeholders with real-time visibility into HOTO delivery progress across all projects, disciplines, and deliverable categories. The dashboard serves as the command center for monitoring OMM deliveries, GDL tracking, and overall platform health through interactive visualizations and data-driven insights.

### API Relationships

**Consumes Data From:**
- HOTO Manager API (`/api/hoto/checklists/summary`)
- RFI Manager API (`/api/rfis/summary`)
- Scheduling Manager API (`/api/schedules/progress`)
- CAD Manager API (`/api/cad/activity`)
- User Service API (`/api/users/me`)

**Provides Data To:**
- None (Dashboard is read-only, consumes aggregated data)

**Integration Points:**
- Navigation links to detail views in other modules
- Filter synchronization with HOTO Manager and RFI Manager
- Real-time data refresh using WebSocket connections for live updates

---

### 1. System Architecture Overview

#### High-Level Architecture
```
┌─────────────────────────────────────────────────────────────┐
│                    Dashboard Frontend                        │
│  ┌───────────┐  ┌───────────┐  ┌────────────┐              │
│  │ OMM Chart │  │ GDL Chart │  │ Progress   │              │
│  │ Component │  │ Component │  │ Component  │              │
│  └─────┬─────┘  └─────┬─────┘  └──────┬─────┘              │
│        │              │                 │                    │
│        └──────────────┴─────────────────┘                    │
│                       │                                      │
│              ┌────────▼─────────┐                           │
│              │  Redux Store     │                           │
│              │  dashboardSlice  │                           │
│              └────────┬─────────┘                           │
│                       │                                      │
│              ┌────────▼──────────┐                          │
│              │ Dashboard Service │                          │
│              └────────┬──────────┘                          │
└───────────────────────┼───────────────────────────────────┘
                        │
                        │ HTTPS/REST
                        │
┌───────────────────────▼───────────────────────────────────┐
│                  Backend API Layer                         │
│  ┌──────────────────────────────────────────────────────┐ │
│  │          DashboardController.java                     │ │
│  │  GET /api/dashboard/overview                          │ │
│  │  GET /api/dashboard/omm-deliveries                    │ │
│  │  GET /api/dashboard/gdl-tracking                      │ │
│  │  GET /api/dashboard/progress-summary                  │ │
│  └────────────────────┬─────────────────────────────────┘ │
│                       │                                     │
│  ┌────────────────────▼─────────────────────────────────┐ │
│  │          DashboardService.java                        │ │
│  │  - aggregateOMMDeliveries()                           │ │
│  │  - calculateGDLProgress()                             │ │
│  │  - getOverallProgress()                               │ │
│  └────────────────────┬─────────────────────────────────┘ │
└────────────────────────┼──────────────────────────────────┘
                         │
                         │ Cosmos DB SDK
                         │
┌────────────────────────▼──────────────────────────────────┐
│              Azure Cosmos DB                               │
│  ┌───────────┐  ┌───────────┐  ┌──────────┐              │
│  │Checklists │  │    RFIs   │  │Schedules │              │
│  │Collection │  │Collection │  │Collection│              │
│  └───────────┘  └───────────┘  └──────────┘              │
└───────────────────────────────────────────────────────────┘
```

#### Technology Stack Justification

**Chart Library: Recharts (React)**
- **Why:** Native React support, declarative API, responsive design
- **Alternatives Considered:** Chart.js (imperative), D3.js (steep learning curve)
- **Decision Factors:** TypeScript support, bundle size (moderate), ease of customization

**Data Aggregation: Backend-Side**
- **Why:** Reduce frontend computational load, consistent business logic
- **Approach:** Pre-aggregate dashboard metrics in scheduled jobs (every 5 minutes)
- **Caching:** Redis cache layer (15-minute TTL) for frequently accessed dashboard data

**Real-Time Updates: Server-Sent Events (SSE)**
- **Why:** Simpler than WebSockets, unidirectional data flow sufficient for dashboard
- **Fallback:** Polling every 30 seconds if SSE not supported
- **Implementation:** Spring WebFlux for reactive streaming

#### Deployment Architecture
```
Azure App Service (Frontend)
  ├── Static React SPA
  ├── CDN: Azure Front Door (Australia Southeast)
  └── Auto-scaling: 2-5 instances based on CPU

Azure App Service (Backend)
  ├── Spring Boot API
  ├── Region: Australia Southeast
  └── Auto-scaling: 2-10 instances based on request volume

Azure Cosmos DB
  ├── SQL API
  ├── Provisioned Throughput: 400-4000 RU/s (auto-scale)
  └── Geo-replication: Single region (cost optimization)

Azure Redis Cache
  ├── Basic tier: 250 MB
  └── Dashboard metrics cache
```

---

### 2. Database Schema Design

#### Entity-Relationship for Dashboard

The Dashboard does not have its own dedicated entities—it aggregates data from existing collections. However, it relies on specific fields and structures:

**Checklist Collection (used by Dashboard)**
```json
{
  "id": "string (UUID)",
  "projectId": "string",
  "checklistName": "string",
  "category": "string (OMM | GDL | HOTO)",
  "status": "string (NOT_STARTED | IN_PROGRESS | COMPLETED)",
  "completionPercentage": "number (0-100)",
  "totalItems": "number",
  "completedItems": "number",
  "assignedTo": "string (userId)",
  "dueDate": "ISO8601 datetime",
  "createdAt": "ISO8601 datetime",
  "updatedAt": "ISO8601 datetime",
  "priority": "string (LOW | MEDIUM | HIGH | CRITICAL)",
  "_partitionKey": "projectId"
}
```

**RFI Collection (used by Dashboard)**
```json
{
  "id": "string (UUID)",
  "projectId": "string",
  "rfiNumber": "string (auto-generated)",
  "status": "string (OPEN | IN_PROGRESS | RESPONDED | CLOSED)",
  "priority": "string (LOW | MEDIUM | HIGH | URGENT)",
  "createdAt": "ISO8601 datetime",
  "responseDeadline": "ISO8601 datetime",
  "respondedAt": "ISO8601 datetime | null",
  "_partitionKey": "projectId"
}
```

**Schedule Collection (used by Dashboard)**
```json
{
  "id": "string (UUID)",
  "projectId": "string",
  "scheduleName": "string",
  "totalTasks": "number",
  "completedTasks": "number",
  "inProgressTasks": "number",
  "delayedTasks": "number",
  "milestones": [
    {
      "name": "string",
      "dueDate": "ISO8601 datetime",
      "status": "string (ON_TRACK | AT_RISK | DELAYED | COMPLETED)"
    }
  ],
  "lastUpdated": "ISO8601 datetime",
  "_partitionKey": "projectId"
}
```

#### Indexing Strategy

**Cosmos DB Composite Indexes for Dashboard Queries:**
```json
{
  "indexingMode": "consistent",
  "automatic": true,
  "includedPaths": [
    { "path": "/*" }
  ],
  "excludedPaths": [
    { "path": "/\"_etag\"/?" }
  ],
  "compositeIndexes": [
    [
      { "path": "/projectId", "order": "ascending" },
      { "path": "/status", "order": "ascending" },
      { "path": "/updatedAt", "order": "descending" }
    ],
    [
      { "path": "/category", "order": "ascending" },
      { "path": "/completionPercentage", "order": "descending" }
    ],
    [
      { "path": "/projectId", "order": "ascending" },
      { "path": "/dueDate", "order": "ascending" }
    ]
  ]
}
```

**Query Performance Optimization:**
- Partition queries by `projectId` to minimize RU consumption
- Pre-aggregate dashboard statistics in a dedicated `DashboardMetrics` collection
- Update metrics collection on each checklist/RFI/schedule status change
- Limit dashboard date range queries to 90 days by default

#### DashboardMetrics Collection (Aggregation Table)
```json
{
  "id": "string (projectId:date)",
  "projectId": "string",
  "metricDate": "ISO8601 date (YYYY-MM-DD)",
  "ommDeliveries": {
    "total": "number",
    "completed": "number",
    "inProgress": "number",
    "notStarted": "number",
    "overdue": "number"
  },
  "gdlTracking": {
    "total": "number",
    "completed": "number",
    "inProgress": "number",
    "notStarted": "number",
    "completionRate": "number (0-100)"
  },
  "hotoProgress": {
    "totalChecklists": "number",
    "completedChecklists": "number",
    "overallPercentage": "number (0-100)"
  },
  "rfiMetrics": {
    "totalRFIs": "number",
    "openRFIs": "number",
    "overdueRFIs": "number",
    "averageResponseTime": "number (hours)"
  },
  "calculatedAt": "ISO8601 datetime",
  "_partitionKey": "projectId"
}
```

---

### 3. Comprehensive API Design

#### API Endpoint: GET /api/dashboard/overview

**Description:** Retrieve comprehensive dashboard overview for all projects or filtered by project

**Authentication:** Required (JWT Bearer Token)

**Authorization:** User must have role `USER`, `PROJECT_MANAGER`, or `ADMIN`

**Request:**
```http
GET /api/dashboard/overview?projectId={projectId}&startDate={YYYY-MM-DD}&endDate={YYYY-MM-DD}
Authorization: Bearer {jwt_token}
```

**Query Parameters:**
| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| projectId | string | No | Filter by specific project (omit for all projects) |
| startDate | date | No | Start date for metrics (default: 30 days ago) |
| endDate | date | No | End date for metrics (default: today) |

**Response (200 OK):**
```json
{
  "success": true,
  "data": {
    "summary": {
      "totalProjects": 12,
      "activeProjects": 8,
      "completedProjects": 4,
      "overdueDeliverables": 15
    },
    "ommDeliveries": {
      "total": 145,
      "completed": 87,
      "inProgress": 42,
      "notStarted": 16,
      "completionRate": 60.0,
      "breakdown": [
        {
          "category": "Mechanical",
          "total": 45,
          "completed": 30,
          "percentage": 66.7
        },
        {
          "category": "Electrical",
          "total": 50,
          "completed": 32,
          "percentage": 64.0
        }
      ]
    },
    "gdlTracking": {
      "total": 234,
      "completed": 178,
      "inProgress": 44,
      "notStarted": 12,
      "completionRate": 76.1,
      "trendData": [
        {
          "date": "2025-11-13",
          "completedItems": 15
        },
        {
          "date": "2025-11-14",
          "completedItems": 22
        }
      ]
    },
    "hotoProgress": {
      "totalChecklists": 56,
      "completedChecklists": 34,
      "overallPercentage": 60.7,
      "byStatus": {
        "completed": 34,
        "inProgress": 18,
        "notStarted": 4
      }
    },
    "rfiSummary": {
      "totalRFIs": 89,
      "openRFIs": 23,
      "overdueRFIs": 7,
      "averageResponseTime": 48.5
    }
  },
  "timestamp": "2025-11-20T10:30:00Z"
}
```

**Response (401 Unauthorized):**
```json
{
  "success": false,
  "error": {
    "code": "UNAUTHORIZED",
    "message": "Authentication required"
  }
}
```

**Response (403 Forbidden):**
```json
{
  "success": false,
  "error": {
    "code": "FORBIDDEN",
    "message": "Insufficient permissions to access dashboard"
  }
}
```

---

#### API Endpoint: GET /api/dashboard/omm-deliveries

**Description:** Retrieve detailed OMM delivery metrics with trend analysis

**Request:**
```http
GET /api/dashboard/omm-deliveries?projectId={projectId}&groupBy={category|discipline}&period={day|week|month}
Authorization: Bearer {jwt_token}
```

**Query Parameters:**
| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| projectId | string | No | Filter by specific project |
| groupBy | string | No | Group results by category or discipline (default: category) |
| period | string | No | Trend period granularity (default: week) |

**Response (200 OK):**
```json
{
  "success": true,
  "data": {
    "totalOMM": 145,
    "completedOMM": 87,
    "completionRate": 60.0,
    "categories": [
      {
        "name": "Mechanical Systems",
        "total": 45,
        "completed": 30,
        "inProgress": 12,
        "notStarted": 3,
        "completionRate": 66.7,
        "overdueItems": 2
      },
      {
        "name": "Electrical Systems",
        "total": 50,
        "completed": 32,
        "inProgress": 15,
        "notStarted": 3,
        "completionRate": 64.0,
        "overdueItems": 3
      }
    ],
    "trends": [
      {
        "period": "2025-W46",
        "completed": 12,
        "added": 5,
        "netProgress": 7
      },
      {
        "period": "2025-W47",
        "completed": 18,
        "added": 3,
        "netProgress": 15
      }
    ],
    "topOverdueItems": [
      {
        "id": "omm-123",
        "name": "HVAC System Documentation",
        "dueDate": "2025-11-15",
        "daysOverdue": 5,
        "assignee": "John Smith"
      }
    ]
  }
}
```

---

#### API Endpoint: GET /api/dashboard/gdl-tracking

**Description:** Retrieve GDL (General Deliverables List) tracking with completion trends

**Request:**
```http
GET /api/dashboard/gdl-tracking?projectId={projectId}&startDate={YYYY-MM-DD}&endDate={YYYY-MM-DD}
Authorization: Bearer {jwt_token}
```

**Response (200 OK):**
```json
{
  "success": true,
  "data": {
    "totalGDL": 234,
    "completedGDL": 178,
    "completionRate": 76.1,
    "statusBreakdown": {
      "completed": 178,
      "inProgress": 44,
      "notStarted": 12,
      "onHold": 0
    },
    "dailyCompletionTrend": [
      {
        "date": "2025-11-13",
        "completed": 15,
        "cumulative": 163
      },
      {
        "date": "2025-11-14",
        "completed": 22,
        "cumulative": 185
      }
    ],
    "projectedCompletion": {
      "estimatedDate": "2026-01-10",
      "daysRemaining": 51,
      "requiredDailyRate": 1.1
    }
  }
}
```

---

#### API Endpoint: GET /api/dashboard/progress-summary

**Description:** Retrieve overall HOTO platform progress across all modules

**Request:**
```http
GET /api/dashboard/progress-summary?projectId={projectId}
Authorization: Bearer {jwt_token}
```

**Response (200 OK):**
```json
{
  "success": true,
  "data": {
    "overallProgress": {
      "totalDeliverables": 524,
      "completedDeliverables": 299,
      "completionPercentage": 57.1
    },
    "moduleProgress": {
      "hotoManager": {
        "checklists": 56,
        "completedChecklists": 34,
        "percentage": 60.7
      },
      "rfiManager": {
        "totalRFIs": 89,
        "closedRFIs": 66,
        "percentage": 74.2
      },
      "schedulingManager": {
        "totalTasks": 234,
        "completedTasks": 145,
        "percentage": 62.0
      },
      "cadManager": {
        "totalDrawings": 45,
        "reviewedDrawings": 32,
        "percentage": 71.1
      }
    },
    "healthIndicators": {
      "overdueItems": 23,
      "atRiskItems": 45,
      "blockedItems": 8,
      "healthScore": 72.5
    }
  }
}
```

---

### Error Handling Strategies

**HTTP Status Codes:**
- `200 OK`: Successful request
- `400 Bad Request`: Invalid query parameters (e.g., invalid date format)
- `401 Unauthorized`: Missing or invalid authentication token
- `403 Forbidden`: User lacks permission to view dashboard
- `404 Not Found`: Project ID not found
- `429 Too Many Requests`: Rate limit exceeded
- `500 Internal Server Error`: Server-side error (logged for investigation)
- `503 Service Unavailable`: Database or external service unavailable

**Error Response Format:**
```json
{
  "success": false,
  "error": {
    "code": "ERROR_CODE",
    "message": "Human-readable error message",
    "details": {
      "field": "fieldName",
      "reason": "Specific validation failure"
    }
  },
  "timestamp": "2025-11-20T10:30:00Z",
  "requestId": "req-uuid-1234"
}
```

---

### Rate Limiting and Caching

**Rate Limiting:**
- Dashboard endpoints: 100 requests per minute per user
- Implementation: Redis-backed token bucket algorithm
- Headers returned: `X-RateLimit-Limit`, `X-RateLimit-Remaining`, `X-RateLimit-Reset`

**Caching Strategy:**
- **Server-Side Cache (Redis):**
  - `/api/dashboard/overview`: 5-minute TTL
  - `/api/dashboard/omm-deliveries`: 10-minute TTL
  - `/api/dashboard/gdl-tracking`: 10-minute TTL
  - Cache invalidation: On checklist/RFI/schedule status change

- **Client-Side Cache:**
  - Redux state: Persist for session duration
  - Stale-while-revalidate: Display cached data while fetching fresh data
  - Auto-refresh: Every 5 minutes when dashboard is active

---

### 4. Frontend Architecture

#### Component Hierarchy

```
DashboardPage
├── DashboardLayout
│   ├── Header
│   │   ├── PageTitle ("Dashboard")
│   │   └── RefreshButton
│   │
│   ├── FilterPanel
│   │   ├── ProjectSelector
│   │   ├── DateRangePicker
│   │   └── ApplyFiltersButton
│   │
│   ├── StatisticsCards (Row 1)
│   │   ├── TotalProjectsCard
│   │   ├── ActiveProjectsCard
│   │   ├── CompletedProjectsCard
│   │   └── OverdueDeliverablesCard
│   │
│   ├── ChartsGrid (Row 2)
│   │   ├── OMMDeliveryChart
│   │   │   ├── ChartHeader
│   │   │   ├── RechartsBarChart
│   │   │   └── LegendComponent
│   │   │
│   │   ├── GDLDeliveryChart
│   │   │   ├── ChartHeader
│   │   │   ├── RechartsLineChart
│   │   │   └── CompletionProjection
│   │   │
│   │   └── OverallProgressChart
│   │       ├── ChartHeader
│   │       ├── RechartsPieChart
│   │       └── PercentageLabel
│   │
│   ├── RFISummarySection (Row 3)
│   │   ├── SectionHeader
│   │   ├── RFIMetricsCards
│   │   └── QuickLinkToRFIManager
│   │
│   └── RecentActivityFeed (Row 4)
│       ├── ActivityList
│       │   └── ActivityItem (repeated)
│       └── ViewAllLink
│
└── Footer
```

#### Reusable Component Library

**1. Card Component**
```typescript
// src/components/common/Card/Card.tsx
interface CardProps {
  title?: string;
  subtitle?: string;
  icon?: React.ReactNode;
  children: React.ReactNode;
  className?: string;
  loading?: boolean;
  error?: string;
  onRefresh?: () => void;
}

export const Card: React.FC<CardProps> = ({
  title,
  subtitle,
  icon,
  children,
  className,
  loading,
  error,
  onRefresh
}) => {
  return (
    <div className={`card ${className}`}>
      {title && (
        <div className="card-header">
          <div className="card-title">
            {icon && <span className="card-icon">{icon}</span>}
            <h3>{title}</h3>
          </div>
          {subtitle && <p className="card-subtitle">{subtitle}</p>}
          {onRefresh && (
            <button onClick={onRefresh} className="card-refresh-btn">
              Refresh
            </button>
          )}
        </div>
      )}
      <div className="card-body">
        {loading ? <Loader /> : error ? <ErrorMessage message={error} /> : children}
      </div>
    </div>
  );
};
```

**CSS for Card Component:**
```css
/* src/components/common/Card/Card.module.css */
.card {
  background: var(--bg-primary);
  border: 1px solid var(--secondary-gray-light);
  border-radius: var(--radius-lg);
  box-shadow: var(--shadow-md);
  padding: var(--spacing-lg);
  transition: box-shadow 0.2s ease;
}

.card:hover {
  box-shadow: var(--shadow-lg);
}

.card-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: var(--spacing-md);
  padding-bottom: var(--spacing-md);
  border-bottom: 1px solid var(--secondary-gray-light);
}

.card-title {
  display: flex;
  align-items: center;
  gap: var(--spacing-sm);
}

.card-title h3 {
  margin: 0;
  font-size: var(--font-size-lg);
  font-weight: var(--font-weight-semibold);
  color: var(--text-primary);
}

.card-icon {
  color: var(--primary-blue);
  font-size: var(--font-size-xl);
}

.card-subtitle {
  margin: var(--spacing-xs) 0 0 0;
  font-size: var(--font-size-sm);
  color: var(--text-secondary);
}

.card-refresh-btn {
  background: none;
  border: 1px solid var(--secondary-gray-light);
  border-radius: var(--radius-md);
  padding: var(--spacing-xs) var(--spacing-sm);
  cursor: pointer;
  color: var(--primary-blue);
  font-size: var(--font-size-sm);
  transition: all 0.2s ease;
}

.card-refresh-btn:hover {
  background: var(--primary-blue);
  color: var(--text-inverse);
  border-color: var(--primary-blue);
}

.card-body {
  min-height: 100px;
}
```

---

**2. StatisticsCard Component**
```typescript
// src/features/dashboard/components/StatisticsCards/StatisticsCard.tsx
interface StatisticsCardProps {
  title: string;
  value: number | string;
  icon: React.ReactNode;
  trend?: {
    value: number;
    direction: 'up' | 'down' | 'neutral';
  };
  color?: 'blue' | 'green' | 'yellow' | 'red';
  loading?: boolean;
}

export const StatisticsCard: React.FC<StatisticsCardProps> = ({
  title,
  value,
  icon,
  trend,
  color = 'blue',
  loading
}) => {
  const trendIcon = trend ? (
    trend.direction === 'up' ? '↑' :
    trend.direction === 'down' ? '↓' : '→'
  ) : null;

  const trendClass = trend ? `trend-${trend.direction}` : '';

  return (
    <div className={`statistics-card statistics-card--${color}`}>
      <div className="statistics-card__icon">{icon}</div>
      <div className="statistics-card__content">
        <h4 className="statistics-card__title">{title}</h4>
        {loading ? (
          <div className="statistics-card__skeleton"></div>
        ) : (
          <>
            <div className="statistics-card__value">{value}</div>
            {trend && (
              <div className={`statistics-card__trend ${trendClass}`}>
                <span className="trend-icon">{trendIcon}</span>
                <span className="trend-value">{Math.abs(trend.value)}%</span>
              </div>
            )}
          </>
        )}
      </div>
    </div>
  );
};
```

**CSS for StatisticsCard:**
```css
/* src/features/dashboard/components/StatisticsCards/StatisticsCard.module.css */
.statistics-card {
  display: flex;
  align-items: center;
  gap: var(--spacing-md);
  background: var(--bg-primary);
  border: 1px solid var(--secondary-gray-light);
  border-radius: var(--radius-lg);
  padding: var(--spacing-lg);
  box-shadow: var(--shadow-sm);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.statistics-card:hover {
  transform: translateY(-2px);
  box-shadow: var(--shadow-md);
}

.statistics-card__icon {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 60px;
  height: 60px;
  border-radius: var(--radius-lg);
  font-size: var(--font-size-2xl);
}

.statistics-card--blue .statistics-card__icon {
  background: rgba(46, 80, 144, 0.1);
  color: var(--primary-blue);
}

.statistics-card--green .statistics-card__icon {
  background: rgba(40, 167, 69, 0.1);
  color: var(--status-success);
}

.statistics-card--yellow .statistics-card__icon {
  background: rgba(255, 193, 7, 0.1);
  color: var(--status-warning);
}

.statistics-card--red .statistics-card__icon {
  background: rgba(220, 53, 69, 0.1);
  color: var(--status-danger);
}

.statistics-card__content {
  flex: 1;
}

.statistics-card__title {
  margin: 0 0 var(--spacing-xs) 0;
  font-size: var(--font-size-sm);
  font-weight: var(--font-weight-medium);
  color: var(--text-secondary);
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.statistics-card__value {
  font-size: var(--font-size-3xl);
  font-weight: var(--font-weight-bold);
  color: var(--text-primary);
  line-height: 1;
  margin-bottom: var(--spacing-xs);
}

.statistics-card__trend {
  display: flex;
  align-items: center;
  gap: var(--spacing-xs);
  font-size: var(--font-size-sm);
  font-weight: var(--font-weight-medium);
}

.trend-up {
  color: var(--status-success);
}

.trend-down {
  color: var(--status-danger);
}

.trend-neutral {
  color: var(--text-secondary);
}

.statistics-card__skeleton {
  width: 80px;
  height: 40px;
  background: linear-gradient(90deg, #f0f0f0 25%, #e0e0e0 50%, #f0f0f0 75%);
  background-size: 200% 100%;
  animation: skeleton-loading 1.5s infinite;
  border-radius: var(--radius-md);
}

@keyframes skeleton-loading {
  0% { background-position: 200% 0; }
  100% { background-position: -200% 0; }
}
```

---

#### State Management Strategy (Redux Toolkit)

**Dashboard Slice:**
```typescript
// src/features/dashboard/slices/dashboardSlice.ts
import { createSlice, createAsyncThunk, PayloadAction } from '@reduxjs/toolkit';
import { dashboardService } from '../services/dashboardService';
import {
  DashboardOverview,
  OMMDeliveries,
  GDLTracking,
  ProgressSummary,
  DashboardFilters
} from '../types/dashboard.types';

interface DashboardState {
  overview: {
    data: DashboardOverview | null;
    loading: boolean;
    error: string | null;
    lastFetched: number | null;
  };
  ommDeliveries: {
    data: OMMDeliveries | null;
    loading: boolean;
    error: string | null;
  };
  gdlTracking: {
    data: GDLTracking | null;
    loading: boolean;
    error: string | null;
  };
  progressSummary: {
    data: ProgressSummary | null;
    loading: boolean;
    error: string | null;
  };
  filters: DashboardFilters;
  autoRefreshEnabled: boolean;
}

const initialState: DashboardState = {
  overview: {
    data: null,
    loading: false,
    error: null,
    lastFetched: null
  },
  ommDeliveries: {
    data: null,
    loading: false,
    error: null
  },
  gdlTracking: {
    data: null,
    loading: false,
    error: null
  },
  progressSummary: {
    data: null,
    loading: false,
    error: null
  },
  filters: {
    projectId: null,
    startDate: null,
    endDate: null
  },
  autoRefreshEnabled: true
};

// Async thunks
export const fetchDashboardOverview = createAsyncThunk(
  'dashboard/fetchOverview',
  async (filters: DashboardFilters, { rejectWithValue }) => {
    try {
      const response = await dashboardService.getOverview(filters);
      return response.data;
    } catch (error: any) {
      return rejectWithValue(error.response?.data?.error?.message || 'Failed to fetch dashboard overview');
    }
  }
);

export const fetchOMMDeliveries = createAsyncThunk(
  'dashboard/fetchOMMDeliveries',
  async (filters: DashboardFilters, { rejectWithValue }) => {
    try {
      const response = await dashboardService.getOMMDeliveries(filters);
      return response.data;
    } catch (error: any) {
      return rejectWithValue(error.response?.data?.error?.message || 'Failed to fetch OMM deliveries');
    }
  }
);

export const fetchGDLTracking = createAsyncThunk(
  'dashboard/fetchGDLTracking',
  async (filters: DashboardFilters, { rejectWithValue }) => {
    try {
      const response = await dashboardService.getGDLTracking(filters);
      return response.data;
    } catch (error: any) {
      return rejectWithValue(error.response?.data?.error?.message || 'Failed to fetch GDL tracking');
    }
  }
);

export const fetchProgressSummary = createAsyncThunk(
  'dashboard/fetchProgressSummary',
  async (projectId: string | null, { rejectWithValue }) => {
    try {
      const response = await dashboardService.getProgressSummary(projectId);
      return response.data;
    } catch (error: any) {
      return rejectWithValue(error.response?.data?.error?.message || 'Failed to fetch progress summary');
    }
  }
);

const dashboardSlice = createSlice({
  name: 'dashboard',
  initialState,
  reducers: {
    setFilters: (state, action: PayloadAction<Partial<DashboardFilters>>) => {
      state.filters = { ...state.filters, ...action.payload };
    },
    clearFilters: (state) => {
      state.filters = initialState.filters;
    },
    toggleAutoRefresh: (state) => {
      state.autoRefreshEnabled = !state.autoRefreshEnabled;
    },
    clearDashboardData: (state) => {
      return initialState;
    }
  },
  extraReducers: (builder) => {
    // Dashboard Overview
    builder.addCase(fetchDashboardOverview.pending, (state) => {
      state.overview.loading = true;
      state.overview.error = null;
    });
    builder.addCase(fetchDashboardOverview.fulfilled, (state, action) => {
      state.overview.loading = false;
      state.overview.data = action.payload;
      state.overview.lastFetched = Date.now();
    });
    builder.addCase(fetchDashboardOverview.rejected, (state, action) => {
      state.overview.loading = false;
      state.overview.error = action.payload as string;
    });

    // OMM Deliveries
    builder.addCase(fetchOMMDeliveries.pending, (state) => {
      state.ommDeliveries.loading = true;
      state.ommDeliveries.error = null;
    });
    builder.addCase(fetchOMMDeliveries.fulfilled, (state, action) => {
      state.ommDeliveries.loading = false;
      state.ommDeliveries.data = action.payload;
    });
    builder.addCase(fetchOMMDeliveries.rejected, (state, action) => {
      state.ommDeliveries.loading = false;
      state.ommDeliveries.error = action.payload as string;
    });

    // GDL Tracking
    builder.addCase(fetchGDLTracking.pending, (state) => {
      state.gdlTracking.loading = true;
      state.gdlTracking.error = null;
    });
    builder.addCase(fetchGDLTracking.fulfilled, (state, action) => {
      state.gdlTracking.loading = false;
      state.gdlTracking.data = action.payload;
    });
    builder.addCase(fetchGDLTracking.rejected, (state, action) => {
      state.gdlTracking.loading = false;
      state.gdlTracking.error = action.payload as string;
    });

    // Progress Summary
    builder.addCase(fetchProgressSummary.pending, (state) => {
      state.progressSummary.loading = true;
      state.progressSummary.error = null;
    });
    builder.addCase(fetchProgressSummary.fulfilled, (state, action) => {
      state.progressSummary.loading = false;
      state.progressSummary.data = action.payload;
    });
    builder.addCase(fetchProgressSummary.rejected, (state, action) => {
      state.progressSummary.loading = false;
      state.progressSummary.error = action.payload as string;
    });
  }
});

export const { setFilters, clearFilters, toggleAutoRefresh, clearDashboardData } = dashboardSlice.actions;
export default dashboardSlice.reducer;
```

---

#### Routing and Navigation Flow

**Route Configuration:**
```typescript
// src/routes/routeConfig.ts
export const routes = {
  dashboard: '/dashboard',
  hotoManager: '/hoto-manager',
  hotoDetail: '/hoto-manager/:checklistId',
  rfiManager: '/rfi-manager',
  rfiDetail: '/rfi-manager/:rfiId',
  scheduling: '/scheduling',
  cadManager: '/cad-manager',
  cadDrawing: '/cad-manager/:drawingId',
  login: '/login',
  profile: '/profile'
};
```

**Dashboard Navigation:**
```typescript
// src/features/dashboard/pages/DashboardPage.tsx
import { useNavigate } from 'react-router-dom';

const DashboardPage = () => {
  const navigate = useNavigate();

  const handleViewChecklistDetails = (checklistId: string) => {
    navigate(`/hoto-manager/${checklistId}`);
  };

  const handleViewRFIDetails = (rfiId: string) => {
    navigate(`/rfi-manager/${rfiId}`);
  };

  // Component implementation...
};
```

---

### 5. Detailed CRUD Operations

The Dashboard is **READ-ONLY**. It does not create, update, or delete data—it aggregates and displays data from other modules.

#### Read Operations

**1. Fetch Dashboard Overview**
- **What:** Retrieve summary statistics across all modules
- **Filtering:** By project, date range
- **Pagination:** Not applicable (always returns summary)
- **Sorting:** Not applicable
- **Response Time Target:** < 500ms (with caching)

**2. Fetch OMM Deliveries**
- **What:** Retrieve OMM delivery progress with category breakdown
- **Filtering:** By project, category, status
- **Pagination:** Not applicable for charts
- **Sorting:** By completion percentage (descending)
- **Response Time Target:** < 300ms

**3. Fetch GDL Tracking**
- **What:** Retrieve GDL completion trends and projections
- **Filtering:** By project, date range
- **Pagination:** Limited to 90 days of trend data
- **Sorting:** By date (ascending for trends)
- **Response Time Target:** < 300ms

**4. Fetch Progress Summary**
- **What:** Retrieve overall platform progress
- **Filtering:** By project
- **Pagination:** Not applicable
- **Sorting:** Not applicable
- **Response Time Target:** < 200ms

---

### 6. User Experience Flow

#### User Journey: Project Manager Reviews Dashboard

**Step 1: Landing on Dashboard**
- User clicks "Dashboard" in navigation sidebar
- System checks authentication (JWT token validation)
- Loading indicator displays while data fetches
- Dashboard renders with default filters (all projects, last 30 days)

**Step 2: Viewing Overview Statistics**
- Four statistics cards display at top:
  1. Total Projects (icon: folder, color: blue)
  2. Active Projects (icon: clock, color: green)
  3. Completed Projects (icon: checkmark, color: green)
  4. Overdue Deliverables (icon: alert, color: red)
- Each card shows value and trend (↑ ↓ →) compared to previous period
- Hover over card shows tooltip with detailed breakdown

**Step 3: Analyzing OMM Deliveries**
- OMM Delivery Chart (Bar Chart) displays categories on X-axis
- Each category shows stacked bars: Completed (green), In Progress (yellow), Not Started (gray)
- Hover over bar segment shows exact count and percentage
- Click on category bar navigates to HOTO Manager filtered by that category
- Legend at bottom allows toggling visibility of status types

**Step 4: Reviewing GDL Tracking**
- GDL Tracking Chart (Line Chart) shows completion trend over time
- X-axis: Dates (last 30 days by default)
- Y-axis: Number of completed items
- Cumulative line shows total completed items
- Dotted projection line shows estimated completion date
- Hover over data point shows exact date and count
- Info icon shows calculation method for projection

**Step 5: Checking Overall Progress**
- Overall Progress Chart (Pie Chart) shows completion breakdown
- Segments: Completed (green), In Progress (yellow), Not Started (gray)
- Center displays overall completion percentage (large font)
- Click on segment highlights related items in activity feed below

**Step 6: Applying Filters**
- User clicks "Filter" button in header
- Filter panel slides down from top
- User selects:
  - Specific project from dropdown
  - Date range (start and end dates)
- User clicks "Apply Filters"
- All charts re-render with filtered data
- Filter badge displays active filters
- "Clear Filters" button appears

**Step 7: Auto-Refresh**
- Dashboard automatically refreshes every 5 minutes (if enabled)
- Small notification appears in top-right: "Data refreshed"
- User can toggle auto-refresh with switch in header
- Manual refresh button always available

**Step 8: Drilling Down**
- User clicks on "23 Open RFIs" in RFI Summary section
- System navigates to RFI Manager with pre-applied filter (status: OPEN)
- User reviews detailed RFI list
- Breadcrumb navigation shows: Dashboard > RFI Manager
- "Back to Dashboard" link available

---

#### State Transitions and Loading States

**Initial Load:**
```
IDLE → LOADING → LOADED | ERROR
```

**Filter Application:**
```
LOADED → FILTERING → FILTERED | ERROR
```

**Auto-Refresh:**
```
LOADED → REFRESHING → LOADED | ERROR
```

**Loading State UI:**
- Statistics cards show skeleton loaders (pulsing gray boxes)
- Charts show spinner in center with "Loading data..." message
- Filter panel disabled during loading
- Partial data never displayed (all-or-nothing approach)

**Error State UI:**
- Error message displayed in place of chart: "Unable to load data. [Retry]"
- Error details logged to console (for debugging)
- Retry button triggers re-fetch
- Other charts continue to display if only one fails

---

### 7. Security Considerations

#### Authentication Flow
1. User provides credentials to `/api/auth/login`
2. Backend validates with Firebase Authentication
3. JWT token generated with claims: `userId`, `role`, `projectIds`
4. Token stored in Redux + localStorage
5. Every API request includes `Authorization: Bearer {token}` header
6. Backend validates token on each request

#### Authorization Matrix

| Role | View All Projects | View Own Projects | Export Data |
|------|------------------|-------------------|-------------|
| ADMIN | ✓ | ✓ | ✓ |
| PROJECT_MANAGER | ✓ | ✓ | ✓ |
| USER | ✗ | ✓ | ✓ |
| STAKEHOLDER | ✗ | ✓ (read-only) | ✗ |
| CLIENT | ✗ | ✓ (limited) | ✗ |

**Project-Level Permissions:**
- Users can only view dashboard data for projects they're assigned to
- `projectIds` claim in JWT token enforces this restriction
- Backend filters all queries by `projectId IN (user.projectIds)`

#### Data Validation and Sanitization

**Query Parameter Validation:**
```java
// DashboardController.java
@GetMapping("/overview")
public ResponseEntity<DashboardOverviewResponse> getOverview(
    @RequestParam(required = false) @Pattern(regexp = "^[a-zA-Z0-9-]+$") String projectId,
    @RequestParam(required = false) @DateTimeFormat(pattern = "yyyy-MM-dd") LocalDate startDate,
    @RequestParam(required = false) @DateTimeFormat(pattern = "yyyy-MM-dd") LocalDate endDate
) {
    // Validate date range
    if (startDate != null && endDate != null && startDate.isAfter(endDate)) {
        throw new ValidationException("startDate must be before endDate");
    }

    // Validate project access
    if (projectId != null && !userHasAccessToProject(projectId)) {
        throw new ForbiddenException("Access denied to project");
    }

    // Process request...
}
```

**Frontend Input Sanitization:**
```typescript
// Date inputs: Validated against ISO 8601 format
// Project IDs: UUID format validation
// No user-generated content on dashboard (read-only)
```

#### Protection Against Common Vulnerabilities

**CSRF Protection:**
- Not applicable for read-only dashboard
- API uses JWT tokens (not cookies), inherently CSRF-resistant

**XSS Protection:**
- All data from API is escaped before rendering
- No `dangerouslySetInnerHTML` used
- CSP headers: `Content-Security-Policy: default-src 'self'; script-src 'self' 'unsafe-inline'; style-src 'self' 'unsafe-inline';`

**SQL Injection:**
- Not applicable (using Cosmos DB with parameterized queries)
- All Cosmos DB queries use SDK query builders, not string concatenation

**Rate Limiting:**
- Prevents DoS attacks
- 100 requests/minute per user
- 429 status code returned when exceeded

---

### 8. Testing Strategy

#### Unit Test Requirements

**Component Tests (React Testing Library):**
```typescript
// src/features/dashboard/components/StatisticsCard/StatisticsCard.test.tsx
import { render, screen } from '@testing-library/react';
import { StatisticsCard } from './StatisticsCard';

describe('StatisticsCard', () => {
  it('renders title and value correctly', () => {
    render(
      <StatisticsCard
        title="Total Projects"
        value={12}
        icon={<FolderIcon />}
        color="blue"
      />
    );

    expect(screen.getByText('Total Projects')).toBeInTheDocument();
    expect(screen.getByText('12')).toBeInTheDocument();
  });

  it('displays trend indicator when provided', () => {
    render(
      <StatisticsCard
        title="Active Projects"
        value={8}
        icon={<ClockIcon />}
        trend={{ value: 12.5, direction: 'up' }}
        color="green"
      />
    );

    expect(screen.getByText('↑')).toBeInTheDocument();
    expect(screen.getByText('12.5%')).toBeInTheDocument();
  });

  it('shows loading skeleton when loading is true', () => {
    render(
      <StatisticsCard
        title="Completed Projects"
        value={4}
        icon={<CheckIcon />}
        loading={true}
      />
    );

    expect(screen.getByTestId('statistics-card-skeleton')).toBeInTheDocument();
  });
});
```

**Redux Slice Tests:**
```typescript
// src/features/dashboard/slices/dashboardSlice.test.ts
import dashboardReducer, {
  fetchDashboardOverview,
  setFilters,
  clearFilters
} from './dashboardSlice';

describe('dashboardSlice', () => {
  const initialState = {
    overview: { data: null, loading: false, error: null, lastFetched: null },
    filters: { projectId: null, startDate: null, endDate: null },
    // ... other state
  };

  it('should set loading state when fetchDashboardOverview is pending', () => {
    const action = { type: fetchDashboardOverview.pending.type };
    const state = dashboardReducer(initialState, action);

    expect(state.overview.loading).toBe(true);
    expect(state.overview.error).toBe(null);
  });

  it('should set data when fetchDashboardOverview is fulfilled', () => {
    const mockData = { summary: { totalProjects: 12 } };
    const action = {
      type: fetchDashboardOverview.fulfilled.type,
      payload: mockData
    };
    const state = dashboardReducer(initialState, action);

    expect(state.overview.loading).toBe(false);
    expect(state.overview.data).toEqual(mockData);
    expect(state.overview.lastFetched).toBeTruthy();
  });

  it('should apply filters correctly', () => {
    const action = setFilters({ projectId: 'project-123', startDate: '2025-11-01' });
    const state = dashboardReducer(initialState, action);

    expect(state.filters.projectId).toBe('project-123');
    expect(state.filters.startDate).toBe('2025-11-01');
  });
});
```

**Service Tests:**
```typescript
// src/features/dashboard/services/dashboardService.test.ts
import { dashboardService } from './dashboardService';
import axios from 'axios';

jest.mock('axios');
const mockedAxios = axios as jest.Mocked<typeof axios>;

describe('dashboardService', () => {
  it('should call correct endpoint for getOverview', async () => {
    const mockResponse = { data: { success: true, data: {} } };
    mockedAxios.get.mockResolvedValue(mockResponse);

    await dashboardService.getOverview({ projectId: 'project-123' });

    expect(mockedAxios.get).toHaveBeenCalledWith(
      '/api/dashboard/overview',
      { params: { projectId: 'project-123' } }
    );
  });

  it('should handle API errors gracefully', async () => {
    mockedAxios.get.mockRejectedValue(new Error('Network error'));

    await expect(
      dashboardService.getOverview({})
    ).rejects.toThrow('Network error');
  });
});
```

---

#### Integration Test Scenarios

**Scenario 1: Dashboard Load with Authentication**
```typescript
// tests/integration/dashboard.test.ts
describe('Dashboard Integration Tests', () => {
  it('should load dashboard data after successful authentication', async () => {
    // 1. Authenticate user
    const loginResponse = await request(app)
      .post('/api/auth/login')
      .send({ email: 'test@example.com', password: 'password123' });

    const token = loginResponse.body.data.token;

    // 2. Fetch dashboard overview
    const dashboardResponse = await request(app)
      .get('/api/dashboard/overview')
      .set('Authorization', `Bearer ${token}`);

    // 3. Verify response
    expect(dashboardResponse.status).toBe(200);
    expect(dashboardResponse.body.success).toBe(true);
    expect(dashboardResponse.body.data.summary).toBeDefined();
  });

  it('should return 401 when accessing dashboard without authentication', async () => {
    const response = await request(app)
      .get('/api/dashboard/overview');

    expect(response.status).toBe(401);
  });
});
```

**Scenario 2: Dashboard Filtering**
```typescript
it('should filter dashboard data by project', async () => {
  const token = await getAuthToken();

  // Fetch all projects
  const allProjectsResponse = await request(app)
    .get('/api/dashboard/overview')
    .set('Authorization', `Bearer ${token}`);

  // Fetch specific project
  const singleProjectResponse = await request(app)
    .get('/api/dashboard/overview?projectId=project-123')
    .set('Authorization', `Bearer ${token}`);

  expect(allProjectsResponse.body.data.summary.totalProjects).toBeGreaterThan(1);
  expect(singleProjectResponse.body.data.summary.totalProjects).toBe(1);
});
```

---

#### End-to-End Test Flows

**E2E Test: Complete Dashboard Interaction**
```typescript
// tests/e2e/dashboard.e2e.test.ts (using Playwright or Cypress)
describe('Dashboard E2E Tests', () => {
  it('should complete full dashboard workflow', async () => {
    // 1. Login
    await page.goto('/login');
    await page.fill('[name="email"]', 'test@example.com');
    await page.fill('[name="password"]', 'password123');
    await page.click('button[type="submit"]');

    // 2. Wait for dashboard to load
    await page.waitForSelector('.statistics-card');

    // 3. Verify statistics cards are displayed
    const totalProjectsCard = await page.locator('.statistics-card').first();
    expect(await totalProjectsCard.isVisible()).toBe(true);

    // 4. Apply filters
    await page.click('button:has-text("Filter")');
    await page.selectOption('select[name="projectId"]', 'project-123');
    await page.fill('input[name="startDate"]', '2025-11-01');
    await page.click('button:has-text("Apply Filters")');

    // 5. Wait for charts to re-render
    await page.waitForSelector('.recharts-wrapper');

    // 6. Verify filter badge is displayed
    const filterBadge = await page.locator('.filter-badge');
    expect(await filterBadge.isVisible()).toBe(true);

    // 7. Click on OMM chart category
    await page.click('.recharts-bar-rectangle >> nth=0');

    // 8. Verify navigation to HOTO Manager
    await page.waitForURL('**/hoto-manager**');
    expect(page.url()).toContain('/hoto-manager');
  });
});
```

---

#### Performance Testing Thresholds

**Load Testing (using k6 or Artillery):**
```javascript
// k6 script for dashboard performance testing
import http from 'k6/http';
import { check, sleep } from 'k6';

export const options = {
  stages: [
    { duration: '1m', target: 50 },  // Ramp up to 50 users
    { duration: '3m', target: 50 },  // Stay at 50 users
    { duration: '1m', target: 100 }, // Ramp up to 100 users
    { duration: '3m', target: 100 }, // Stay at 100 users
    { duration: '1m', target: 0 },   // Ramp down to 0 users
  ],
  thresholds: {
    http_req_duration: ['p(95)<500'], // 95% of requests under 500ms
    http_req_failed: ['rate<0.01'],   // Error rate under 1%
  },
};

export default function () {
  const token = 'Bearer YOUR_JWT_TOKEN';
  const headers = { Authorization: token };

  // Test dashboard overview endpoint
  const overviewRes = http.get('https://api.hoto.com/api/dashboard/overview', { headers });
  check(overviewRes, {
    'overview status is 200': (r) => r.status === 200,
    'overview response time < 500ms': (r) => r.timings.duration < 500,
  });

  sleep(1);
}
```

**Performance Targets:**
- **Page Load Time:** < 2 seconds (initial render)
- **Time to Interactive:** < 3 seconds
- **API Response Time:** < 500ms (95th percentile)
- **Chart Rendering:** < 200ms
- **Filter Application:** < 300ms

---

### 9. Data Management

#### Data Lifecycle Policies

**Dashboard Metrics Aggregation:**
- **Calculation Frequency:** Every 5 minutes (cron job)
- **Data Retention:** 90 days of daily aggregations
- **Archival:** After 90 days, aggregate to monthly summaries
- **Deletion:** Monthly summaries deleted after 2 years

**Cache Expiration:**
- **Redis Cache TTL:** 5-15 minutes depending on data type
- **Client-Side Cache:** Session duration (cleared on logout)
- **Stale-While-Revalidate:** Display cached data while fetching fresh data

**Data Refresh Strategy:**
```typescript
// Pseudo-code for cache management
const getCachedData = async (cacheKey, fetchFunction, ttl) => {
  const cachedData = await redis.get(cacheKey);

  if (cachedData) {
    // Return cached data immediately
    const parsedData = JSON.parse(cachedData);

    // Check if cache is stale (> 50% of TTL)
    if (parsedData.cachedAt + (ttl * 0.5) < Date.now()) {
      // Revalidate in background (fire-and-forget)
      fetchFunction().then(freshData => {
        redis.set(cacheKey, JSON.stringify(freshData), ttl);
      });
    }

    return parsedData;
  } else {
    // Fetch fresh data
    const freshData = await fetchFunction();
    await redis.set(cacheKey, JSON.stringify(freshData), ttl);
    return freshData;
  }
};
```

---

#### Caching Strategies

**Multi-Level Caching:**

**Level 1: Browser Cache**
- Static assets (JS, CSS, images): 1 year cache
- Cache-Control: `public, max-age=31536000, immutable`
- Versioned filenames (e.g., `main.abc123.js`) for cache busting

**Level 2: Redux Store (Client Memory)**
- Dashboard data cached in Redux state
- Persisted to localStorage for page refreshes
- Invalidated on logout or explicit refresh

**Level 3: CDN Cache (Azure Front Door)**
- API responses cached at edge locations
- Cache-Control: `public, max-age=300` (5 minutes)
- Purge cache on data updates (via Azure SDK)

**Level 4: Application Cache (Redis)**
- Aggregated dashboard metrics cached
- TTL: 5-15 minutes based on data type
- Invalidated on relevant data changes

**Cache Invalidation Strategy:**
```java
// Backend: Invalidate cache when checklist status changes
@Service
public class ChecklistService {
  @Autowired
  private RedisTemplate<String, String> redisTemplate;

  public void updateChecklistStatus(String checklistId, ChecklistStatus newStatus) {
    // Update database
    checklistRepository.updateStatus(checklistId, newStatus);

    // Invalidate related dashboard caches
    String projectId = getProjectIdByChecklist(checklistId);
    String cacheKey = "dashboard:overview:" + projectId;
    redisTemplate.delete(cacheKey);

    // Trigger metrics recalculation
    dashboardMetricsService.recalculateForProject(projectId);
  }
}
```

---

#### Pagination and Infinite Scrolling

**Dashboard Pagination:**
- Not applicable for main dashboard (always shows summary)
- Trend charts limited to 90 data points (90 days)
- "View More" link navigates to detailed module (e.g., RFI Manager)

**Lazy Loading:**
- Charts rendered only when scrolled into viewport
- Intersection Observer API used for detection
- Skeleton loaders displayed before data loads

---

#### Real-Time Data Requirements

**Update Frequency:**
- **Critical Data:** Real-time (< 5 seconds) - Overdue deliverables count
- **Important Data:** Near real-time (< 1 minute) - Checklist status changes
- **Standard Data:** Periodic (5 minutes) - Overall statistics

**Implementation: Server-Sent Events (SSE)**
```typescript
// Frontend: Subscribe to dashboard updates
import { useEffect } from 'react';

const useDashboardLiveUpdates = (projectId: string) => {
  useEffect(() => {
    const eventSource = new EventSource(`/api/dashboard/live-updates?projectId=${projectId}`);

    eventSource.onmessage = (event) => {
      const update = JSON.parse(event.data);

      // Dispatch Redux action to update specific metric
      dispatch(updateDashboardMetric(update));
    };

    eventSource.onerror = (error) => {
      console.error('SSE connection error:', error);
      eventSource.close();

      // Fallback to polling
      startPolling();
    };

    return () => {
      eventSource.close();
    };
  }, [projectId]);
};
```

**Backend: SSE Endpoint**
```java
// DashboardController.java
@GetMapping(value = "/live-updates", produces = MediaType.TEXT_EVENT_STREAM_VALUE)
public Flux<ServerSentEvent<DashboardUpdate>> streamDashboardUpdates(
    @RequestParam String projectId,
    @AuthenticationPrincipal UserDetails userDetails
) {
    return dashboardService.streamUpdates(projectId)
        .map(update -> ServerSentEvent.<DashboardUpdate>builder()
            .data(update)
            .build());
}
```

---

### 10. Error Handling & Logging

#### Structured Logging Format

**Log Entry Structure:**
```json
{
  "timestamp": "2025-11-20T10:30:45.123Z",
  "level": "INFO | WARN | ERROR | DEBUG",
  "service": "dashboard-api",
  "requestId": "req-uuid-1234",
  "userId": "user-uuid-5678",
  "method": "GET",
  "endpoint": "/api/dashboard/overview",
  "responseTime": 245,
  "statusCode": 200,
  "message": "Dashboard overview fetched successfully",
  "metadata": {
    "projectId": "project-123",
    "filters": { "startDate": "2025-11-01", "endDate": "2025-11-20" }
  }
}
```

**Backend Logging:**
```java
// DashboardController.java
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;

@RestController
@RequestMapping("/api/dashboard")
public class DashboardController {
  private static final Logger logger = LoggerFactory.getLogger(DashboardController.class);

  @GetMapping("/overview")
  public ResponseEntity<DashboardOverviewResponse> getOverview(
      @RequestParam(required = false) String projectId,
      @RequestHeader("X-Request-ID") String requestId
  ) {
    long startTime = System.currentTimeMillis();

    try {
      logger.info("Fetching dashboard overview - requestId: {}, projectId: {}",
                  requestId, projectId);

      DashboardOverviewResponse response = dashboardService.getOverview(projectId);

      long responseTime = System.currentTimeMillis() - startTime;
      logger.info("Dashboard overview fetched successfully - requestId: {}, responseTime: {}ms",
                  requestId, responseTime);

      return ResponseEntity.ok(response);

    } catch (Exception e) {
      long responseTime = System.currentTimeMillis() - startTime;
      logger.error("Error fetching dashboard overview - requestId: {}, responseTime: {}ms, error: {}",
                   requestId, responseTime, e.getMessage(), e);
      throw e;
    }
  }
}
```

**Frontend Logging:**
```typescript
// src/utils/logger.ts
export enum LogLevel {
  DEBUG = 'DEBUG',
  INFO = 'INFO',
  WARN = 'WARN',
  ERROR = 'ERROR'
}

interface LogEntry {
  timestamp: string;
  level: LogLevel;
  message: string;
  metadata?: Record<string, any>;
}

class Logger {
  private log(level: LogLevel, message: string, metadata?: Record<string, any>) {
    const entry: LogEntry = {
      timestamp: new Date().toISOString(),
      level,
      message,
      metadata: {
        ...metadata,
        userAgent: navigator.userAgent,
        url: window.location.href
      }
    };

    // Console logging (development)
    if (process.env.NODE_ENV === 'development') {
      console.log(entry);
    }

    // Send to backend logging service (production)
    if (process.env.NODE_ENV === 'production' && level !== LogLevel.DEBUG) {
      this.sendToBackend(entry);
    }
  }

  private sendToBackend(entry: LogEntry) {
    // Fire-and-forget POST request to logging endpoint
    fetch('/api/logs/frontend', {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify(entry)
    }).catch(console.error); // Silently fail if logging service is down
  }

  info(message: string, metadata?: Record<string, any>) {
    this.log(LogLevel.INFO, message, metadata);
  }

  warn(message: string, metadata?: Record<string, any>) {
    this.log(LogLevel.WARN, message, metadata);
  }

  error(message: string, metadata?: Record<string, any>) {
    this.log(LogLevel.ERROR, message, metadata);
  }

  debug(message: string, metadata?: Record<string, any>) {
    this.log(LogLevel.DEBUG, message, metadata);
  }
}

export const logger = new Logger();
```

---

#### Error Classification and Prioritization

**Error Categories:**

| Category | Severity | Response | Example |
|----------|----------|----------|---------|
| Authentication Failure | CRITICAL | Log + Alert + Block Access | Invalid JWT token |
| Authorization Failure | HIGH | Log + Return 403 | User accessing unauthorized project |
| Data Fetch Failure | MEDIUM | Log + Retry + Show Error UI | Cosmos DB timeout |
| Validation Error | LOW | Log + Return 400 | Invalid date format |
| Client-Side Error | MEDIUM | Log + Report to Backend | Chart rendering failure |

**Error Prioritization Matrix:**
```
CRITICAL (P0): System down, authentication broken, data corruption
HIGH (P1): Major feature broken, significant user impact
MEDIUM (P2): Minor feature broken, workaround available
LOW (P3): Cosmetic issues, minimal user impact
```

---

#### Monitoring and Alerting Thresholds

**Azure Application Insights Alerts:**

**Alert 1: High Error Rate**
- **Condition:** Error rate > 5% over 5 minutes
- **Action:** Send email + PagerDuty alert
- **Severity:** Critical

**Alert 2: Slow Response Time**
- **Condition:** P95 response time > 1000ms over 10 minutes
- **Action:** Send email to dev team
- **Severity:** Warning

**Alert 3: High CPU Usage**
- **Condition:** App Service CPU > 80% over 15 minutes
- **Action:** Auto-scale + Send email
- **Severity:** Warning

**Alert 4: Cosmos DB Throttling**
- **Condition:** 429 responses > 10 over 5 minutes
- **Action:** Increase RU/s + Send email
- **Severity:** High

**Custom Dashboard Metrics:**
```typescript
// Frontend: Track dashboard performance metrics
import { trackMetric } from '@azure/application-insights-web';

const trackDashboardLoad = (loadTime: number) => {
  trackMetric({
    name: 'DashboardLoadTime',
    value: loadTime,
    properties: {
      page: 'Dashboard',
      user: getCurrentUserId()
    }
  });
};

const trackChartRenderTime = (chartType: string, renderTime: number) => {
  trackMetric({
    name: 'ChartRenderTime',
    value: renderTime,
    properties: {
      chartType,
      dataPoints: getDataPointCount()
    }
  });
};
```

---

#### Recovery Mechanisms

**Automatic Retry Logic:**
```typescript
// src/utils/apiRetry.ts
export const fetchWithRetry = async (
  fetchFunction: () => Promise<any>,
  maxRetries: number = 3,
  delayMs: number = 1000
): Promise<any> => {
  let lastError: Error;

  for (let attempt = 1; attempt <= maxRetries; attempt++) {
    try {
      return await fetchFunction();
    } catch (error: any) {
      lastError = error;

      // Don't retry on client errors (4xx)
      if (error.response?.status >= 400 && error.response?.status < 500) {
        throw error;
      }

      // Wait before retrying (exponential backoff)
      if (attempt < maxRetries) {
        const delay = delayMs * Math.pow(2, attempt - 1);
        await new Promise(resolve => setTimeout(resolve, delay));

        logger.warn(`Retrying request (attempt ${attempt + 1}/${maxRetries})`, {
          error: error.message,
          delay
        });
      }
    }
  }

  logger.error('All retry attempts failed', { error: lastError.message });
  throw lastError;
};
```

**Circuit Breaker Pattern:**
```typescript
// src/utils/circuitBreaker.ts
class CircuitBreaker {
  private failureCount = 0;
  private lastFailureTime: number | null = null;
  private state: 'CLOSED' | 'OPEN' | 'HALF_OPEN' = 'CLOSED';

  constructor(
    private readonly threshold: number = 5,
    private readonly timeout: number = 60000 // 1 minute
  ) {}

  async execute<T>(operation: () => Promise<T>): Promise<T> {
    if (this.state === 'OPEN') {
      if (Date.now() - this.lastFailureTime! > this.timeout) {
        this.state = 'HALF_OPEN';
      } else {
        throw new Error('Circuit breaker is OPEN');
      }
    }

    try {
      const result = await operation();
      this.onSuccess();
      return result;
    } catch (error) {
      this.onFailure();
      throw error;
    }
  }

  private onSuccess() {
    this.failureCount = 0;
    this.state = 'CLOSED';
  }

  private onFailure() {
    this.failureCount++;
    this.lastFailureTime = Date.now();

    if (this.failureCount >= this.threshold) {
      this.state = 'OPEN';
    }
  }
}
```

**Graceful Degradation:**
- If live data unavailable, display last cached data with "Displaying cached data" notice
- If chart rendering fails, display data in table format
- If specific metric unavailable, show "N/A" instead of breaking entire dashboard

---

### Design Styles Required

#### Dashboard-Specific Styles

**Dashboard Grid Layout:**
```css
/* src/features/dashboard/pages/DashboardPage.module.css */
.dashboard-page {
  padding: var(--spacing-xl);
  background: var(--bg-secondary);
  min-height: 100vh;
}

.dashboard-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: var(--spacing-xl);
}

.dashboard-title {
  font-size: var(--font-size-3xl);
  font-weight: var(--font-weight-bold);
  color: var(--text-primary);
  margin: 0;
}

.dashboard-actions {
  display: flex;
  gap: var(--spacing-md);
}

/* Statistics Cards Row */
.statistics-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: var(--spacing-lg);
  margin-bottom: var(--spacing-xl);
}

/* Charts Grid */
.charts-grid {
  display: grid;
  grid-template-columns: repeat(12, 1fr);
  gap: var(--spacing-lg);
  margin-bottom: var(--spacing-xl);
}

.chart-card--full {
  grid-column: span 12;
}

.chart-card--half {
  grid-column: span 6;
}

.chart-card--third {
  grid-column: span 4;
}

@media (max-width: 768px) {
  .chart-card--half,
  .chart-card--third {
    grid-column: span 12;
  }
}

/* Filter Panel */
.filter-panel {
  background: var(--bg-primary);
  border: 1px solid var(--secondary-gray-light);
  border-radius: var(--radius-lg);
  padding: var(--spacing-lg);
  margin-bottom: var(--spacing-xl);
  box-shadow: var(--shadow-md);
}

.filter-panel__row {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: var(--spacing-md);
  margin-bottom: var(--spacing-md);
}

.filter-panel__actions {
  display: flex;
  justify-content: flex-end;
  gap: var(--spacing-md);
}
```

**Chart Container Styles:**
```css
/* src/features/dashboard/components/Charts/ChartContainer.module.css */
.chart-container {
  background: var(--bg-primary);
  border: 1px solid var(--secondary-gray-light);
  border-radius: var(--radius-lg);
  padding: var(--spacing-lg);
  box-shadow: var(--shadow-md);
  height: 400px;
  display: flex;
  flex-direction: column;
}

.chart-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: var(--spacing-md);
  padding-bottom: var(--spacing-md);
  border-bottom: 1px solid var(--secondary-gray-light);
}

.chart-title {
  font-size: var(--font-size-xl);
  font-weight: var(--font-weight-semibold);
  color: var(--text-primary);
  margin: 0;
}

.chart-subtitle {
  font-size: var(--font-size-sm);
  color: var(--text-secondary);
  margin: var(--spacing-xs) 0 0 0;
}

.chart-body {
  flex: 1;
  position: relative;
  min-height: 250px;
}

.chart-empty {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100%;
  color: var(--text-secondary);
}

.chart-empty__icon {
  font-size: var(--font-size-3xl);
  margin-bottom: var(--spacing-md);
  opacity: 0.5;
}

.chart-empty__message {
  font-size: var(--font-size-lg);
}
```

**Recharts Custom Styling:**
```css
/* Override Recharts default styles */
.recharts-wrapper {
  font-family: var(--font-primary);
}

.recharts-cartesian-axis-tick {
  font-size: var(--font-size-sm);
  fill: var(--text-secondary);
}

.recharts-legend-wrapper {
  font-size: var(--font-size-sm);
}

.recharts-tooltip-wrapper {
  border-radius: var(--radius-md);
  box-shadow: var(--shadow-lg);
}

.custom-tooltip {
  background: var(--bg-primary);
  border: 1px solid var(--secondary-gray-light);
  border-radius: var(--radius-md);
  padding: var(--spacing-md);
  box-shadow: var(--shadow-lg);
}

.custom-tooltip__label {
  font-weight: var(--font-weight-semibold);
  color: var(--text-primary);
  margin-bottom: var(--spacing-sm);
}

.custom-tooltip__item {
  display: flex;
  align-items: center;
  gap: var(--spacing-sm);
  margin-bottom: var(--spacing-xs);
  font-size: var(--font-size-sm);
}

.custom-tooltip__color {
  width: 12px;
  height: 12px;
  border-radius: var(--radius-sm);
}
```

---

### Implementation Checklist

- [ ] Set up dashboard route and page component
- [ ] Create Redux slice for dashboard state management
- [ ] Implement dashboard service for API calls
- [ ] Build StatisticsCard component with tests
- [ ] Build Card component with loading and error states
- [ ] Integrate Recharts library
- [ ] Create OMMDeliveryChart component (Bar Chart)
- [ ] Create GDLDeliveryChart component (Line Chart)
- [ ] Create OverallProgressChart component (Pie Chart)
- [ ] Implement FilterPanel component
- [ ] Build backend DashboardController
- [ ] Build backend DashboardService with business logic
- [ ] Create DashboardMetrics aggregation collection
- [ ] Implement Redis caching layer
- [ ] Set up Server-Sent Events for real-time updates
- [ ] Configure composite indexes in Cosmos DB
- [ ] Write unit tests for components
- [ ] Write unit tests for Redux slice
- [ ] Write integration tests for API endpoints
- [ ] Write E2E tests for dashboard flow
- [ ] Set up Application Insights monitoring
- [ ] Configure alert rules in Azure
- [ ] Implement rate limiting
- [ ] Implement error handling and logging
- [ ] Create user documentation for dashboard
- [ ] Performance testing and optimization

---

## Feature 2: HOTO Manager Module

### Feature Goal
Enable project teams to create, track, and manage comprehensive handover checklists with DCP (Document Control Plan) item tracking. Provide a systematic approach to ensuring all deliverables are completed on schedule with clear accountability and progress visibility.

### API Relationships

**Consumes Data From:**
- User Service API (`/api/users`) - For assignee information
- Project Service API (`/api/projects`) - For project details
- Authentication API (`/api/auth`) - For permissions

**Provides Data To:**
- Dashboard API (`/api/dashboard/overview`) - Checklist summary and completion metrics
- Dashboard API (`/api/dashboard/omm-deliveries`) - OMM delivery statistics

**Integration Points:**
- Dashboard navigation links filter to specific checklists
- Export functionality generates Excel/PDF reports
- Email notifications sent when items assigned or completed
- Audit trail logs all checklist changes

---

### 1. System Architecture Overview

#### High-Level Architecture
```
┌─────────────────────────────────────────────────────────────┐
│                  HOTO Manager Frontend                       │
│  ┌───────────────┐  ┌────────────────┐  ┌───────────────┐  │
│  │  Checklist    │  │  Checklist     │  │ DCP Item      │  │
│  │  List View    │  │  Detail View   │  │ Tracker       │  │
│  │ (Handsontable)│  │ (Handsontable) │  │               │  │
│  └───────┬───────┘  └────────┬───────┘  └───────┬───────┘  │
│          │                   │                   │           │
│          └───────────────────┴───────────────────┘           │
│                              │                                │
│                    ┌─────────▼─────────┐                     │
│                    │   Redux Store     │                     │
│                    │   hotoSlice       │                     │
│                    └─────────┬─────────┘                     │
│                              │                                │
│                    ┌─────────▼──────────┐                    │
│                    │   HOTO Service     │                    │
│                    └─────────┬──────────┘                    │
└──────────────────────────────┼───────────────────────────────┘
                               │ HTTPS/REST
                               │
┌──────────────────────────────▼───────────────────────────────┐
│                    Backend API Layer                          │
│  ┌──────────────────────────────────────────────────────────┐│
│  │               HotoController.java                         ││
│  │  GET    /api/hoto/checklists                              ││
│  │  POST   /api/hoto/checklists                              ││
│  │  GET    /api/hoto/checklists/{id}                         ││
│  │  PUT    /api/hoto/checklists/{id}                         ││
│  │  DELETE /api/hoto/checklists/{id}                         ││
│  │  PATCH  /api/hoto/checklists/{id}/items/{itemId}/status   ││
│  │  GET    /api/hoto/checklists/{id}/export/excel            ││
│  │  GET    /api/hoto/checklists/{id}/export/pdf              ││
│  └────────────────────────┬─────────────────────────────────┘│
│                           │                                    │
│  ┌────────────────────────▼─────────────────────────────────┐│
│  │            ChecklistService.java                          ││
│  │  - createChecklist()                                      ││
│  │  - updateChecklistItem()                                  ││
│  │  - calculateCompletionPercentage()                        ││
│  │  - assignItemToUser()                                     ││
│  │  - exportToExcel()                                        ││
│  │  - exportToPDF()                                          ││
│  └────────────────────────┬─────────────────────────────────┘│
└────────────────────────────┼──────────────────────────────────┘
                             │ Cosmos DB SDK
                             │
┌────────────────────────────▼──────────────────────────────────┐
│                    Azure Cosmos DB                             │
│  ┌────────────────┐  ┌──────────────┐  ┌─────────────────┐   │
│  │   Checklists   │  │ ChecklistItems│  │   DCPItems      │   │
│  │   Collection   │  │  (embedded)   │  │   Collection    │   │
│  └────────────────┘  └──────────────┘  └─────────────────┘   │
└───────────────────────────────────────────────────────────────┘
```

#### Technology Stack Justification

**Grid Component: Handsontable**
- **Why:** Excel-like interface familiar to project managers, advanced features (sorting, filtering, inline editing)
- **Alternatives Considered:** AG Grid (expensive), React Table (lacks Excel UX)
- **Decision Factors:** Copy/paste support, keyboard navigation, cell validation, formula support
- **License:** Commercial license required for production use

**Data Structure: Embedded vs. Separate Collections**
- **Approach:** Checklist items embedded within Checklist document
- **Why:** Atomic updates, better query performance for single checklist retrieval
- **Trade-off:** Larger document size, but Cosmos DB supports up to 2MB per document

**Export Libraries:**
- **Excel Export:** Apache POI (Java) for server-side .xlsx generation
- **PDF Export:** iText PDF or Apache PDFBox for server-side PDF generation

---

### 2. Database Schema Design

#### Checklist Collection

**Collection Name:** `Checklists`
**Partition Key:** `projectId`

**Schema:**
```json
{
  "id": "checklist-uuid-1234",
  "projectId": "project-abc-123",
  "checklistName": "Mechanical Systems HOTO Checklist",
  "checklistNumber": "HOTO-2025-001",
  "category": "OMM",
  "discipline": "Mechanical",
  "status": "IN_PROGRESS",
  "priority": "HIGH",
  "description": "Comprehensive checklist for mechanical systems handover",
  "completionPercentage": 65.5,
  "totalItems": 45,
  "completedItems": 29,
  "inProgressItems": 12,
  "notStartedItems": 4,
  "createdBy": "user-uuid-5678",
  "assignedTo": "user-uuid-9101",
  "createdAt": "2025-11-15T08:30:00Z",
  "updatedAt": "2025-11-20T14:22:00Z",
  "dueDate": "2026-01-15T00:00:00Z",
  "items": [
    {
      "itemId": "item-uuid-0001",
      "itemNumber": "1.1",
      "description": "HVAC System Documentation Complete",
      "category": "Documentation",
      "status": "COMPLETED",
      "priority": "HIGH",
      "assignedTo": "user-uuid-3456",
      "completedBy": "user-uuid-3456",
      "completedAt": "2025-11-18T16:45:00Z",
      "dueDate": "2025-11-20T00:00:00Z",
      "notes": "All manuals submitted and approved",
      "dcpReference": "DCP-MECH-001",
      "attachments": [
        {
          "id": "attach-uuid-001",
          "fileName": "HVAC_Manual.pdf",
          "fileSize": 2458624,
          "fileType": "application/pdf",
          "uploadedBy": "user-uuid-3456",
          "uploadedAt": "2025-11-18T16:40:00Z",
          "blobUrl": "https://hotostorage.blob.core.windows.net/attachments/hvac_manual.pdf"
        }
      ],
      "dependencies": ["item-uuid-0002"],
      "createdAt": "2025-11-15T08:30:00Z",
      "updatedAt": "2025-11-18T16:45:00Z"
    },
    {
      "itemId": "item-uuid-0002",
      "itemNumber": "1.2",
      "description": "Commissioning Certificates Submitted",
      "category": "Certification",
      "status": "IN_PROGRESS",
      "priority": "HIGH",
      "assignedTo": "user-uuid-7890",
      "dueDate": "2025-11-22T00:00:00Z",
      "notes": "Waiting for final sign-off from contractor",
      "dcpReference": "DCP-MECH-002",
      "attachments": [],
      "dependencies": [],
      "createdAt": "2025-11-15T08:30:00Z",
      "updatedAt": "2025-11-19T10:15:00Z"
    }
  ],
  "history": [
    {
      "timestamp": "2025-11-18T16:45:00Z",
      "userId": "user-uuid-3456",
      "action": "ITEM_COMPLETED",
      "itemId": "item-uuid-0001",
      "description": "Marked item 1.1 as completed"
    }
  ],
  "tags": ["mechanical", "hoto", "priority"],
  "_partitionKey": "project-abc-123"
}
```

**Field Definitions:**

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| id | string (UUID) | Yes | Unique checklist identifier |
| projectId | string | Yes | Project identifier (partition key) |
| checklistName | string | Yes | Human-readable checklist name |
| checklistNumber | string | Yes | Auto-generated unique number |
| category | enum | Yes | OMM \| GDL \| HOTO \| GENERAL |
| discipline | string | No | Engineering discipline (Mechanical, Electrical, etc.) |
| status | enum | Yes | NOT_STARTED \| IN_PROGRESS \| COMPLETED \| ON_HOLD |
| priority | enum | Yes | LOW \| MEDIUM \| HIGH \| CRITICAL |
| description | string | No | Detailed checklist description |
| completionPercentage | number | Yes | Calculated: (completedItems / totalItems) * 100 |
| totalItems | number | Yes | Count of all items in checklist |
| completedItems | number | Yes | Count of items with status COMPLETED |
| assignedTo | string (userId) | No | Primary responsible person |
| dueDate | ISO8601 | No | Target completion date |
| items | array[ChecklistItem] | Yes | Embedded checklist items |
| history | array[HistoryEntry] | Yes | Audit trail of all changes |

---

#### DCP Items Collection

**Collection Name:** `DCPItems`
**Partition Key:** `projectId`

```json
{
  "id": "dcp-uuid-1234",
  "projectId": "project-abc-123",
  "dcpNumber": "DCP-MECH-001",
  "title": "HVAC System Documentation Package",
  "description": "Complete documentation package for HVAC systems",
  "discipline": "Mechanical",
  "status": "APPROVED",
  "submittedBy": "user-uuid-3456",
  "reviewedBy": "user-uuid-9999",
  "submittedDate": "2025-11-18T16:40:00Z",
  "approvedDate": "2025-11-18T17:30:00Z",
  "documents": [
    {
      "documentId": "doc-uuid-001",
      "documentNumber": "DOC-HVAC-001",
      "documentTitle": "HVAC Operation Manual",
      "revision": "Rev C",
      "fileUrl": "https://hotostorage.blob.core.windows.net/dcp/hvac_manual_revC.pdf"
    }
  ],
  "relatedChecklistItems": ["item-uuid-0001"],
  "_partitionKey": "project-abc-123"
}
```

---

#### Indexing Strategy

**Composite Indexes for Checklist Queries:**
```json
{
  "compositeIndexes": [
    [
      { "path": "/projectId", "order": "ascending" },
      { "path": "/status", "order": "ascending" },
      { "path": "/dueDate", "order": "ascending" }
    ],
    [
      { "path": "/projectId", "order": "ascending" },
      { "path": "/category", "order": "ascending" },
      { "path": "/completionPercentage", "order": "descending" }
    ],
    [
      { "path": "/assignedTo", "order": "ascending" },
      { "path": "/status", "order": "ascending" }
    ],
    [
      { "path": "/projectId", "order": "ascending" },
      { "path": "/checklistNumber", "order": "ascending" }
    ]
  ]
}
```

**Query Optimization:**
- Use `projectId` in all queries to leverage partition key
- Limit embedded `items` array to 500 items per checklist
- For large checklists, implement pagination on item retrieval
- Cache frequently accessed checklists in Redis (5-minute TTL)

---

### 3. Comprehensive API Design

#### API Endpoint: GET /api/hoto/checklists

**Description:** Retrieve list of checklists with filtering, sorting, and pagination

**Request:**
```http
GET /api/hoto/checklists?projectId={id}&status={status}&category={category}&page={page}&pageSize={size}&sortBy={field}&sortOrder={asc|desc}
Authorization: Bearer {jwt_token}
```

**Query Parameters:**
| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| projectId | string | No | Filter by project ID |
| status | string | No | Filter by status (NOT_STARTED, IN_PROGRESS, COMPLETED) |
| category | string | No | Filter by category (OMM, GDL, HOTO) |
| assignedTo | string | No | Filter by assigned user ID |
| search | string | No | Search in checklist name and description |
| page | number | No | Page number (default: 1) |
| pageSize | number | No | Items per page (default: 20, max: 100) |
| sortBy | string | No | Sort field (default: updatedAt) |
| sortOrder | string | No | asc or desc (default: desc) |

**Response (200 OK):**
```json
{
  "success": true,
  "data": {
    "checklists": [
      {
        "id": "checklist-uuid-1234",
        "checklistName": "Mechanical Systems HOTO Checklist",
        "checklistNumber": "HOTO-2025-001",
        "category": "OMM",
        "status": "IN_PROGRESS",
        "completionPercentage": 65.5,
        "totalItems": 45,
        "completedItems": 29,
        "assignedTo": {
          "userId": "user-uuid-9101",
          "name": "John Smith",
          "email": "john.smith@example.com"
        },
        "dueDate": "2026-01-15T00:00:00Z",
        "updatedAt": "2025-11-20T14:22:00Z"
      }
    ],
    "pagination": {
      "currentPage": 1,
      "pageSize": 20,
      "totalItems": 156,
      "totalPages": 8,
      "hasNextPage": true,
      "hasPreviousPage": false
    }
  }
}
```

---

#### API Endpoint: POST /api/hoto/checklists

**Description:** Create a new checklist

**Request:**
```http
POST /api/hoto/checklists
Authorization: Bearer {jwt_token}
Content-Type: application/json

{
  "projectId": "project-abc-123",
  "checklistName": "Electrical Systems HOTO Checklist",
  "category": "OMM",
  "discipline": "Electrical",
  "priority": "HIGH",
  "description": "Electrical handover checklist",
  "assignedTo": "user-uuid-5555",
  "dueDate": "2026-01-20T00:00:00Z",
  "items": [
    {
      "itemNumber": "1.1",
      "description": "Electrical Drawings Submitted",
      "category": "Documentation",
      "priority": "HIGH",
      "assignedTo": "user-uuid-6666",
      "dueDate": "2025-12-15T00:00:00Z",
      "dcpReference": "DCP-ELEC-001"
    },
    {
      "itemNumber": "1.2",
      "description": "Testing Certificates Complete",
      "category": "Certification",
      "priority": "HIGH",
      "assignedTo": "user-uuid-7777",
      "dueDate": "2025-12-20T00:00:00Z"
    }
  ]
}
```

**Validation Rules:**
- `checklistName`: Required, 3-200 characters
- `category`: Required, must be valid enum value
- `projectId`: Required, must exist in Projects collection
- `items`: Array, 1-500 items
- `assignedTo`: Must be valid user ID
- `dueDate`: Must be future date

**Response (201 Created):**
```json
{
  "success": true,
  "data": {
    "id": "checklist-uuid-5678",
    "checklistNumber": "HOTO-2025-002",
    "checklistName": "Electrical Systems HOTO Checklist",
    "status": "NOT_STARTED",
    "completionPercentage": 0,
    "totalItems": 2,
    "createdAt": "2025-11-20T15:00:00Z"
  },
  "message": "Checklist created successfully"
}
```

**Response (400 Bad Request):**
```json
{
  "success": false,
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Validation failed",
    "details": [
      {
        "field": "checklistName",
        "reason": "Checklist name is required"
      },
      {
        "field": "items",
        "reason": "At least one checklist item is required"
      }
    ]
  }
}
```

---

#### API Endpoint: PATCH /api/hoto/checklists/{id}/items/{itemId}/status

**Description:** Update the status of a specific checklist item

**Request:**
```http
PATCH /api/hoto/checklists/checklist-uuid-1234/items/item-uuid-0002/status
Authorization: Bearer {jwt_token}
Content-Type: application/json

{
  "status": "COMPLETED",
  "notes": "All commissioning certificates received and verified",
  "completedBy": "user-uuid-7890"
}
```

**Response (200 OK):**
```json
{
  "success": true,
  "data": {
    "itemId": "item-uuid-0002",
    "status": "COMPLETED",
    "completedAt": "2025-11-20T15:30:00Z",
    "completedBy": "user-uuid-7890",
    "checklistCompletionPercentage": 68.9
  },
  "message": "Item status updated successfully"
}
```

**Side Effects:**
- Recalculates checklist `completionPercentage`
- Updates `updatedAt` timestamp on parent checklist
- Adds entry to checklist `history` array
- Triggers email notification to checklist owner
- Invalidates dashboard cache for this project

---

#### API Endpoint: GET /api/hoto/checklists/{id}/export/excel

**Description:** Export checklist to Excel (.xlsx) format

**Request:**
```http
GET /api/hoto/checklists/checklist-uuid-1234/export/excel
Authorization: Bearer {jwt_token}
```

**Response (200 OK):**
```http
Content-Type: application/vnd.openxmlformats-officedocument.spreadsheetml.sheet
Content-Disposition: attachment; filename="HOTO-2025-001_Checklist.xlsx"

[Binary Excel file data]
```

**Excel File Structure:**
- **Sheet 1: Summary**
  - Checklist name, number, status
  - Completion percentage
  - Key statistics (total items, completed, in progress)
  - Assigned to, due date

- **Sheet 2: Items**
  - Table with columns: Item #, Description, Category, Status, Priority, Assigned To, Due Date, Notes
  - Color-coded rows by status (green=completed, yellow=in progress, red=overdue)
  - Frozen header row
  - Filters enabled on all columns

- **Sheet 3: History**
  - Audit trail of all changes
  - Columns: Timestamp, User, Action, Description

---

#### API Endpoint: GET /api/hoto/checklists/{id}/export/pdf

**Description:** Export checklist to PDF format

**Request:**
```http
GET /api/hoto/checklists/checklist-uuid-1234/export/pdf
Authorization: Bearer {jwt_token}
```

**Response (200 OK):**
```http
Content-Type: application/pdf
Content-Disposition: attachment; filename="HOTO-2025-001_Checklist.pdf"

[Binary PDF file data]
```

**PDF File Structure:**
- **Header:** Company logo, checklist name, number, date generated
- **Summary Section:** Key metrics and statistics
- **Items Table:** All checklist items with formatting
- **Footer:** Page numbers, generated by user, timestamp

---

### 4. Frontend Architecture

#### Component Hierarchy

```
HOTOManagerPage
├── ChecklistListView
│   ├── PageHeader
│   │   ├── Title ("HOTO Manager")
│   │   └── CreateChecklistButton
│   │
│   ├── FilterBar
│   │   ├── ProjectFilter
│   │   ├── StatusFilter
│   │   ├── CategoryFilter
│   │   └── SearchInput
│   │
│   ├── ChecklistTable (Handsontable)
│   │   ├── Columns: Name, Number, Category, Status, Progress, Assigned To, Due Date
│   │   ├── ContextMenu (Right-click)
│   │   ├── InlineEditing
│   │   └── BulkActions
│   │
│   └── PaginationControls
│
└── ChecklistDetailView
    ├── ChecklistHeader
    │   ├── BackButton
    │   ├── ChecklistInfo
    │   ├── ProgressBar
    │   └── ActionButtons (Export, Delete)
    │
    ├── ItemsTable (Handsontable)
    │   ├── Columns: Item #, Description, Status, Priority, Assigned To, Due Date, Notes
    │   ├── InlineEditing
    │   ├── StatusDropdown
    │   ├── DatePicker
    │   └── AssigneeSelector
    │
    ├── DCPReferencePanel
    │   └── LinkedDCPItems
    │
    ├── AttachmentsPanel
    │   ├── FileUploader
    │   └── AttachmentList
    │
    └── HistoryPanel
        └── AuditTrail
```

---

#### Handsontable Integration

**Installation:**
```bash
npm install handsontable @handsontable/react
```

**Checklist List Table Configuration:**
```typescript
// src/features/hoto-manager/components/ChecklistTable/ChecklistTable.tsx
import { HotTable } from '@handsontable/react';
import { registerAllModules } from 'handsontable/registry';
import 'handsontable/dist/handsontable.full.min.css';

registerAllModules();

interface ChecklistTableProps {
  checklists: Checklist[];
  onChecklistClick: (id: string) => void;
  onStatusChange: (id: string, newStatus: string) => void;
}

export const ChecklistTable: React.FC<ChecklistTableProps> = ({
  checklists,
  onChecklistClick,
  onStatusChange
}) => {
  const columns = [
    {
      data: 'checklistNumber',
      title: 'Checklist #',
      type: 'text',
      readOnly: true,
      width: 120
    },
    {
      data: 'checklistName',
      title: 'Checklist Name',
      type: 'text',
      width: 250,
      renderer: (instance, td, row, col, prop, value, cellProperties) => {
        td.innerHTML = `<a href="#" class="checklist-link">${value}</a>`;
        td.classList.add('htMiddle');
        return td;
      }
    },
    {
      data: 'category',
      title: 'Category',
      type: 'dropdown',
      source: ['OMM', 'GDL', 'HOTO', 'GENERAL'],
      width: 100
    },
    {
      data: 'status',
      title: 'Status',
      type: 'dropdown',
      source: ['NOT_STARTED', 'IN_PROGRESS', 'COMPLETED', 'ON_HOLD'],
      width: 120,
      renderer: (instance, td, row, col, prop, value, cellProperties) => {
        const statusColors = {
          NOT_STARTED: '#9BA3AB',
          IN_PROGRESS: '#FFC107',
          COMPLETED: '#28A745',
          ON_HOLD: '#DC3545'
        };
        td.style.backgroundColor = statusColors[value] || '#FFFFFF';
        td.style.color = '#FFFFFF';
        td.style.fontWeight = '600';
        td.style.textAlign = 'center';
        td.innerHTML = value.replace('_', ' ');
        return td;
      }
    },
    {
      data: 'completionPercentage',
      title: 'Progress',
      type: 'numeric',
      numericFormat: {
        pattern: '0.0%',
        culture: 'en-US'
      },
      width: 100,
      renderer: (instance, td, row, col, prop, value, cellProperties) => {
        const percentage = Math.round(value);
        const color = percentage >= 75 ? '#28A745' : percentage >= 50 ? '#FFC107' : '#DC3545';

        td.innerHTML = `
          <div class="progress-cell">
            <div class="progress-bar" style="width: 100%; background: #E8EAED; height: 20px; border-radius: 4px;">
              <div style="width: ${percentage}%; background: ${color}; height: 100%; border-radius: 4px;"></div>
            </div>
            <span class="progress-text">${percentage}%</span>
          </div>
        `;
        return td;
      }
    },
    {
      data: 'assignedTo.name',
      title: 'Assigned To',
      type: 'text',
      width: 150
    },
    {
      data: 'dueDate',
      title: 'Due Date',
      type: 'date',
      dateFormat: 'YYYY-MM-DD',
      correctFormat: true,
      width: 120,
      renderer: (instance, td, row, col, prop, value, cellProperties) => {
        if (value) {
          const dueDate = new Date(value);
          const today = new Date();
          const isOverdue = dueDate < today && checklists[row].status !== 'COMPLETED';

          td.innerHTML = dueDate.toLocaleDateString('en-US', {
            year: 'numeric',
            month: 'short',
            day: 'numeric'
          });

          if (isOverdue) {
            td.style.color = '#DC3545';
            td.style.fontWeight = '600';
          }
        }
        return td;
      }
    }
  ];

  const settings = {
    data: checklists,
    columns: columns,
    colHeaders: true,
    rowHeaders: true,
    height: 600,
    licenseKey: process.env.REACT_APP_HANDSONTABLE_LICENSE,
    stretchH: 'all',
    filters: true,
    dropdownMenu: true,
    contextMenu: ['row_above', 'row_below', 'remove_row', '---------', 'copy', 'cut'],
    manualColumnResize: true,
    manualRowResize: true,
    fixedColumnsLeft: 2,
    afterChange: (changes, source) => {
      if (source === 'edit' && changes) {
        changes.forEach(([row, prop, oldValue, newValue]) => {
          if (prop === 'status' && oldValue !== newValue) {
            const checklistId = checklists[row].id;
            onStatusChange(checklistId, newValue);
          }
        });
      }
    },
    afterOnCellMouseDown: (event, coords, TD) => {
      if (coords.col === 1 && coords.row >= 0) { // Checklist Name column
        const checklistId = checklists[coords.row].id;
        onChecklistClick(checklistId);
      }
    }
  };

  return (
    <div className="checklist-table-container">
      <HotTable settings={settings} />
    </div>
  );
};
```

**Custom CSS for Handsontable:**
```css
/* src/features/hoto-manager/components/ChecklistTable/ChecklistTable.module.css */
.checklist-table-container {
  background: var(--bg-primary);
  border: 1px solid var(--secondary-gray-light);
  border-radius: var(--radius-lg);
  padding: var(--spacing-lg);
  box-shadow: var(--shadow-md);
}

.checklist-table-container .handsontable {
  font-family: var(--font-primary);
  font-size: var(--font-size-sm);
}

.checklist-table-container .handsontable th {
  background: var(--bg-secondary);
  font-weight: var(--font-weight-semibold);
  color: var(--text-primary);
  border-color: var(--secondary-gray-light);
}

.checklist-table-container .handsontable td {
  border-color: var(--secondary-gray-light);
}

.checklist-table-container .handsontable .currentRow {
  background: rgba(46, 80, 144, 0.05);
}

.checklist-table-container .htCheckboxRendererInput {
  vertical-align: middle;
}

.checklist-link {
  color: var(--primary-blue);
  text-decoration: none;
  font-weight: var(--font-weight-medium);
}

.checklist-link:hover {
  text-decoration: underline;
}

.progress-cell {
  display: flex;
  align-items: center;
  gap: var(--spacing-sm);
}

.progress-text {
  font-weight: var(--font-weight-semibold);
  min-width: 40px;
}
```

---

### 5. Detailed CRUD Operations

#### Create Checklist
**Process:**
1. User clicks "Create Checklist" button
2. Modal dialog opens with form:
   - Checklist name (required)
   - Category dropdown (required)
   - Discipline (optional)
   - Priority (required)
   - Description (optional)
   - Assigned to (user selector)
   - Due date (date picker)
3. User adds checklist items:
   - Click "Add Item" button
   - Fill item details in modal
   - Items added to temporary list
4. User clicks "Create Checklist"
5. Frontend validates all fields
6. POST request to `/api/hoto/checklists`
7. Backend creates checklist with auto-generated number
8. Success notification displayed
9. Navigate to checklist detail view

**Validation:**
- Checklist name: 3-200 characters
- At least 1 checklist item required
- All item descriptions required
- Due date must be future date (warning only)

---

#### Read Checklists (List View)
**Process:**
1. User navigates to HOTO Manager
2. Frontend fetches checklists: `GET /api/hoto/checklists?projectId={id}`
3. Handsontable renders checklists in grid
4. User can:
   - Sort by clicking column headers
   - Filter using dropdown menu
   - Search using search bar
   - Paginate through results

**Performance Optimization:**
- Server-side pagination (20 items per page)
- Debounced search input (300ms delay)
- Virtual scrolling for large datasets

---

#### Read Checklist Detail
**Process:**
1. User clicks on checklist name in list view
2. Navigate to `/hoto-manager/{checklistId}`
3. Frontend fetches detailed checklist: `GET /api/hoto/checklists/{id}`
4. Display checklist header with summary
5. Render checklist items in Handsontable
6. Load DCP references, attachments, and history in separate panels

**Data Display:**
- Header: Name, number, status, progress bar
- Items table: All checklist items with inline editing
- Side panels: DCP references, attachments, audit history

---

#### Update Checklist Item Status
**Process:**
1. User selects item status from dropdown in Handsontable
2. Confirmation modal appears (optional, for COMPLETED status)
3. User adds completion notes (required for COMPLETED)
4. PATCH request to `/api/hoto/checklists/{id}/items/{itemId}/status`
5. Backend updates item status
6. Backend recalculates completion percentage
7. Frontend updates displayed data
8. Success notification shown

**Real-time Updates:**
- Other users viewing same checklist receive update via SSE
- Toast notification: "Item 1.2 marked as completed by John Smith"

---

#### Delete Checklist
**Process:**
1. User clicks "Delete" button in checklist detail view
2. Confirmation modal: "Are you sure? This cannot be undone."
3. User confirms deletion
4. DELETE request to `/api/hoto/checklists/{id}`
5. Backend performs soft delete (sets `deleted: true`, `deletedAt: timestamp`)
6. Navigate back to checklist list view
7. Success notification: "Checklist deleted successfully"

**Security:**
- Only ADMIN or checklist creator can delete
- Soft delete allows recovery if needed
- Hard delete after 30 days (automated cleanup job)

---

### 6. User Experience Flow

#### User Journey: Create and Track Checklist

**Step 1: Creating Checklist**
- Click "Create Checklist" button (top-right)
- Modal opens with form
- Fill in checklist details
- Add items one by one using "Add Item" button
- Each item has: description, category, priority, assignee, due date
- Preview items in table below form
- Click "Create" button

**Step 2: Viewing Checklist List**
- Land on HOTO Manager page
- See all checklists in Handsontable grid
- Columns: #, Name, Category, Status, Progress, Assigned To, Due Date
- Apply filters: Status dropdown, Category dropdown
- Search by name
- Sort by clicking column headers
- Overdue checklists highlighted in red

**Step 3: Editing Checklist Items**
- Click on checklist name to open detail view
- Handsontable displays all items
- Double-click cell to edit inline
- Tab to navigate between cells
- Status dropdown: NOT_STARTED, IN_PROGRESS, COMPLETED
- Date picker for due dates
- User selector for assignees
- Changes auto-save after edit

**Step 4: Marking Item Complete**
- Select "COMPLETED" from status dropdown
- Modal appears: "Add completion notes"
- User enters notes
- Click "Mark Complete"
- Progress bar updates
- Notification sent to checklist owner

**Step 5: Tracking Progress**
- Return to list view
- See updated completion percentage (e.g., 68.9%)
- Progress bar color: Green (>75%), Yellow (50-75%), Red (<50%)
- Dashboard reflects updated metrics

**Step 6: Exporting Checklist**
- Click "Export" dropdown in detail view
- Select "Export to Excel" or "Export to PDF"
- File downloads automatically
- Filename: `HOTO-2025-001_Checklist.xlsx`

---

### 7. Security Considerations

#### Authorization Rules
- **View Checklists:** User must be assigned to project OR have role ADMIN/PROJECT_MANAGER
- **Create Checklist:** USER, PROJECT_MANAGER, ADMIN roles
- **Edit Checklist:** Checklist creator, assigned user, or ADMIN
- **Delete Checklist:** Checklist creator or ADMIN only
- **Export Checklist:** Any user with view access

#### Data Protection
- All API requests require valid JWT token
- Project-level access control enforced
- Audit trail logs all changes with user ID and timestamp
- File attachments scanned for viruses before upload

---

### 8. Testing Strategy

**Unit Tests:**
- Checklist creation validation
- Completion percentage calculation
- Status change logic
- Export functionality

**Integration Tests:**
- API endpoint testing
- Database queries
- Email notification triggers

**E2E Tests:**
- Complete checklist creation flow
- Item status update flow
- Export to Excel flow
- Filtering and sorting

---

### 9. Design Styles

**Checklist List View:**
```css
.hoto-manager-page {
  padding: var(--spacing-xl);
  background: var(--bg-secondary);
}

.page-header {
  display: flex;
  justify-content: space-between;
  margin-bottom: var(--spacing-xl);
}

.create-btn {
  background: var(--primary-blue);
  color: var(--text-inverse);
  border: none;
  padding: var(--spacing-sm) var(--spacing-lg);
  border-radius: var(--radius-md);
  font-weight: var(--font-weight-semibold);
  cursor: pointer;
}

.create-btn:hover {
  background: var(--primary-blue-dark);
}
```

---

### Implementation Checklist

- [ ] Set up HOTO Manager routes
- [ ] Create Redux slice for checklist management
- [ ] Implement HOTO service for API calls
- [ ] Install and configure Handsontable
- [ ] Build ChecklistTable component
- [ ] Build ChecklistDetailView component
- [ ] Implement create checklist modal
- [ ] Implement item status update logic
- [ ] Build export to Excel functionality
- [ ] Build export to PDF functionality
- [ ] Create backend HotoController
- [ ] Create backend ChecklistService
- [ ] Implement file attachment upload
- [ ] Set up email notifications
- [ ] Write unit tests
- [ ] Write integration tests
- [ ] Write E2E tests

---



## Feature 3: RFI Manager Module

### Feature Goal
Streamline the Request for Information (RFI) process by providing a centralized system for creating, tracking, and responding to RFIs with automated email notifications, document attachments, DWG markup capabilities, and comprehensive reporting.

**Note:** Due to the comprehensive nature and length (RFI Manager specification would add ~2,500 lines), I'll create a summary here. The full detailed specification following the same format as Dashboard and HOTO Manager is ready to be added. Would you like me to continue with full detail or proceed with the remaining modules (Scheduling Manager and CAD Manager) first?

### Key Components
- Handsontable grid for RFI list management
- DWG annotation viewer with layer sidebar (left panel)
- Annotation tools: Arrow, Circle, Rectangle, Freehand, Text, Highlight
- Email notification system (Azure Communications Services)
- Response threading
- PDF/Excel export
- File attachments

### Critical Technical Details
- **DWG Rendering:** Simplified viewer for RFI context (full capabilities in CAD Manager)
- **Layer Panel:** Left sidebar showing all DWG layers with visibility toggles
- **Annotation Canvas:** HTML5 Canvas overlay for markup
- **Email Templates:** HTML templates for RFI created, response added, closed notifications

---

