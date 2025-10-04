# SETU - Temple & Pilgrimage Crowd Management System
## Design Guidelines

### Design Approach: Material Design System
**Rationale**: SETU is a mission-critical, data-intensive government application requiring enterprise-grade reliability, clear information hierarchy, and real-time data visualization. Material Design provides the robust component library and established patterns needed for complex dashboards and administrative interfaces.

---

## Core Design Elements

### A. Color Palette

**Primary Colors:**
- Primary: 26 80% 45% (Deep temple saffron/orange - cultural resonance with Indian pilgrimage sites)
- Primary Variant: 26 70% 35% (Darker shade for headers and emphasis)

**Functional Colors:**
- Success: 142 71% 45% (Queue cleared, low crowd density)
- Warning: 38 92% 50% (Moderate crowd levels)
- Danger: 0 84% 60% (High crowd density, alerts)
- Info: 217 91% 60% (System notifications, guidance)

**Neutrals:**
- Background: 0 0% 98% (Light mode primary)
- Surface: 0 0% 100% (Card backgrounds)
- Text Primary: 0 0% 13%
- Text Secondary: 0 0% 46%

**Dark Mode:**
- Background: 0 0% 7%
- Surface: 0 0% 12%
- Text Primary: 0 0% 95%
- Text Secondary: 0 0% 70%

### B. Typography

**Font Family**: Inter (Google Fonts) - exceptional readability for data-heavy interfaces
- Headings: 600-700 weight
- Body: 400 weight
- Data/Numbers: 500-600 weight (tabular numerals)

**Scale:**
- H1: 2.5rem (Dashboard titles)
- H2: 2rem (Section headers)
- H3: 1.5rem (Card titles)
- Body: 1rem (Standard content)
- Small: 0.875rem (Metadata, timestamps)
- Caption: 0.75rem (Labels, micro-copy)

### C. Layout System

**Spacing Primitives**: Tailwind units of 2, 4, 6, 8, 12, 16
- Component padding: p-4, p-6
- Section gaps: gap-6, gap-8
- Page margins: m-8, m-12
- Card spacing: p-6

**Grid Structure:**
- Dashboard: 12-column grid with responsive breakpoints
- Sidebar: 280px fixed (desktop), collapsible (mobile)
- Main content: max-w-7xl centered

### D. Component Library

**Navigation:**
- Persistent sidebar with temple locations, analytics, queue management, alerts
- Top app bar with user profile, notifications bell (with badge counter), global search
- Breadcrumb navigation for deep pages

**Data Visualization:**
- Real-time crowd density heatmaps using Google Maps integration
- Line charts for historical crowd patterns (Chart.js or Recharts)
- Gauge meters for current capacity levels (0-100%)
- Status indicators with color-coded badges (Low/Moderate/High/Critical)

**Core Components:**
- Elevated cards with shadow-md for dashboard widgets
- Data tables with sorting, filtering, pagination
- Alert banners (info/warning/critical) with dismiss actions
- Modal dialogs for queue management actions
- Bottom sheets (mobile) for quick actions

**Forms & Controls:**
- Material-style text fields with floating labels
- Toggle switches for system controls (auto-alerts, drone activation)
- Date/time pickers for report generation
- Multi-select dropdowns for temple filtering

**Interactive Elements:**
- Floating Action Button (FAB) for primary actions (e.g., "Create Alert")
- Icon buttons from Material Icons for table actions
- Chip components for filtering and tags
- Progress indicators for data loading states

### E. Dashboard Layout Strategy

**Primary Dashboard View:**
- Hero metrics strip: 4-column grid showing live counts (Current Visitors, Queue Length, Average Wait Time, Drone Status)
- Live temple map: Full-width interactive map with color-coded crowd density overlays
- Quick action cards: 3-column grid (Queue Management, Alert System, Reports)
- Recent activity feed: Timeline of system events and alerts

**Temple-Specific Pages:**
- Split view: Map on left (60%), real-time stats on right (40%)
- Entrance/exit flow visualization
- Prasad distribution queue status
- Parking availability indicators

**Analytics Section:**
- Date range selector at top
- Multi-line graph comparing crowd patterns across temples
- Peak time predictions table
- Export functionality for reports

### F. Mobile Responsiveness

**Breakpoints:**
- Mobile: < 640px (single column, bottom navigation)
- Tablet: 640-1024px (collapsible sidebar)
- Desktop: > 1024px (persistent sidebar)

**Mobile Optimizations:**
- Bottom navigation bar with 4 primary sections
- Swipeable temple cards
- Simplified map view with tap-to-expand details
- Voice alerts for critical crowd situations

---

## Images

**No hero images required** - this is a functional dashboard application prioritizing data visualization over marketing imagery.

**Operational Images:**
- Temple icons/logos for each location (Somnath, Dwarka, Ambaji, Pavagadh) in sidebar and map markers
- Live camera feeds (if available) embedded in temple detail views
- Drone surveillance thumbnails in monitoring section

**Iconography:**
- Material Icons via CDN for all UI controls
- Custom temple silhouettes for location identifiers
- Status icons: crowd levels, alerts, queue status

---

## Accessibility & Dark Mode

- Maintain WCAG 2.1 AA contrast standards across all color combinations
- Dark mode toggle in user menu - persistent across sessions
- All form inputs styled consistently in both modes with clear focus states
- High-contrast mode option for outdoor/bright light usage

---

## Animation Principles

**Minimal, Purposeful Motion:**
- Smooth transitions (150-200ms) for state changes only
- Loading skeletons for data fetching
- Ripple effects on button presses (Material Design standard)
- NO decorative animations - this is a real-time monitoring system requiring focus