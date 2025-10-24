# YouTube Creator Tools Dashboard - Design Guidelines

## Design Approach: Reference-Based
**Primary Reference**: User-provided HTML template with dark purple theme
**Secondary Inspiration**: Modern dashboard interfaces (Linear, Notion) for tool organization

This project uses an **exact visual continuation** of the provided design system - maintaining all existing styles, colors, and components while extending them for a tools dashboard layout.

---

## Core Visual System (From Provided Template)

### Color Palette (DO NOT MODIFY)
```
Primary: #5b5ff5 (blue-violet)
Background Dark: #1e1e2f
Background Light: #2c2c40
Card Background: #383850
Text Light: #f0f0f5
Text Secondary: #a0a0b0

Status Colors (NEW):
- Available: #5aa667 (green - from existing minecraft-green)
- In Development: #f39c12 (orange)
- Maintenance: #e74c3c (red)
```

### Typography
- Font Stack: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif
- H1: 3rem, bold (2.2rem mobile)
- H2: 2rem, 700 weight
- H3: 1.5rem
- Body: 1rem, 500 weight
- Navigation: 1rem, 500 weight

### Spacing System
Use Tailwind units: 2, 4, 8, 12, 16, 20, 24, 32, 40
- Card padding: 40px standard, 30px sides
- Section gaps: 50px
- Card gaps in grid: 30px
- Navigation padding: 15px 30px

---

## Layout Structure

### Navigation Bar (EXACT COPY)
- Height: 70px fixed
- Logo on left (image height: 60px)
- Navigation links on right with icons
- Items: Accueil (home icon) | Creator Studio (chart icon - ACTIVE) | Discord | Serveur MC
- Same hover effects and active states as template

### Main Content Area
- Full-width container with centered max-width: 1200px
- Padding: 40px vertical, 20px horizontal
- Vertical layout with 50px gaps between sections

### Tools Grid Layout
**Desktop (≥1024px)**: 3 columns
**Tablet (768px-1023px)**: 2 columns  
**Mobile (<768px)**: 1 column

Grid gap: 30px between cards
Each card: Equal height, flexible width

---

## Component Library

### Tool Card
**Structure:**
- Background: #2c2c40 (--background-light)
- Border-radius: 15px
- Box-shadow: 0 10px 25px rgba(0, 0, 0, 0.25)
- Border: 1px solid rgba(91, 95, 245, 0.2)
- Padding: 30px
- Transition: transform 0.3s ease

**Card Contents (top to bottom):**
1. **Icon Area**: Font Awesome icon (2.5rem size, primary color)
2. **Tool Name**: H3 styling, 1.5rem, 700 weight, text-light color
3. **Description**: Paragraph, 1rem, text-secondary color, 2-3 lines max
4. **Status Badge**: Pill-shaped indicator at bottom

**Hover State:**
- Transform: translateY(-5px)
- Enhanced shadow: 0 15px 30px rgba(91, 95, 245, 0.3)

### Status Badge Component
**Positioning**: Bottom of card, full-width

**Badge Styling:**
- Padding: 12px 20px
- Border-radius: 8px
- Font-size: 0.95rem
- Font-weight: 600
- Text-align: center
- Display: flex with icon

**Three States:**

1. **Available**
   - Background: rgba(90, 166, 103, 0.2)
   - Text/Icon: #5aa667
   - Icon: fa-check-circle
   - Text: "Disponible"

2. **In Development**
   - Background: rgba(243, 156, 18, 0.2)
   - Text/Icon: #f39c12
   - Icon: fa-code
   - Text: "En développement"

3. **Maintenance**
   - Background: rgba(231, 76, 60, 0.2)
   - Text/Icon: #e74c3c
   - Icon: fa-tools
   - Text: "Maintenance"

### Page Header Section
- Same structure as template's "connection-card"
- H1: "Outils pour Créateurs YouTube"
- Subtitle: Description of tools dashboard
- Center-aligned text

---

## Tool Categories & Organization

Display tools in a single unified grid (not categorized sections) for clean, scannable layout.

**Suggested Tools (8-12 total):**
- Thumbnail Generator (Development)
- Analytics Dashboard (Available)
- Video Scheduler (Available)
- Title Optimizer (Development)
- Tag Generator (Available)
- Thumbnail A/B Tester (Maintenance)
- Script Writer Assistant (Development)
- Comment Manager (Available)
- SEO Analyzer (Available)
- Monetization Tracker (Development)

---

## Interactive Elements

### Navigation Items (From Template)
- Padding: 8px 12px
- Border-radius: 6px
- Hover: background primary-color, text background-dark, translateY(-2px)
- Icon margin-right: 8px

### Tool Cards
- Cursor: pointer on hover
- No click functionality needed (static page)
- Visual feedback through transform and shadow

---

## Responsive Behavior

### Desktop (≥1024px)
- 3-column grid
- Full navigation bar horizontal
- 40px vertical padding

### Tablet (768px-1023px)
- 2-column grid
- Navigation may wrap
- 30px vertical padding

### Mobile (<768px)
- 1-column grid
- Navigation stacks vertically
- Logo centers above nav links
- 20px vertical padding
- H1: 2.2rem
- Card padding: 25px

---

## Icons
**Library**: Font Awesome 6.5.2 (already integrated via CDN in template)

**Tool Icons (suggestions):**
- Thumbnail: fa-image
- Analytics: fa-chart-line
- Scheduler: fa-clock
- Title: fa-heading
- Tags: fa-tags
- A/B Test: fa-flask
- Script: fa-file-lines
- Comments: fa-comments
- SEO: fa-search
- Monetization: fa-dollar-sign

---

## Additional UI Elements

### Empty State (if needed)
- Icon: fa-tools (3rem, text-secondary)
- Message: "Aucun outil disponible pour le moment"
- Same card styling as tool cards

### Loading State (optional)
- Pulse animation on card backgrounds
- Skeleton loader matching card dimensions

---

## Accessibility
- Maintain 4.5:1 contrast ratios (already met in template)
- Status badges include both icon and text
- Keyboard navigation follows template patterns
- Alt text for logo: "LeNoobInconnu STUDIO"

---

## Critical Requirements
1. **Zero deviation** from provided color scheme
2. **Exact match** of navigation bar structure and behavior
3. **Consistent** card styling with template's connection-card and version-box patterns
4. **Same** Font Awesome integration method
5. **Identical** hover effects and transitions timing