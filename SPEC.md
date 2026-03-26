# Portfolio Website Specification

## 1. Project Overview
- **Project Name**: Interactive Portfolio
- **Type**: Single-page website
- **Core Functionality**: A visually striking portfolio showcasing projects with interactive animations and modern design
- **Target Users**: Potential clients, employers, and collaborators

## 2. UI/UX Specification

### Layout Structure
- **Navbar**: Fixed top, full-width, height 70px, contains logo and navigation links
- **Hero Section**: Full viewport height, centered glassmorphism card
- **Projects Section**: Grid of 4 project cards (2x2 on desktop, 1 column on mobile)
- **Footer**: Simple centered footer with social links

### Responsive Breakpoints
- Mobile: < 768px
- Tablet: 768px - 1024px
- Desktop: > 1024px

### Visual Design

#### Color Palette
- **Background**: `#0a0a0f` (Deep Charcoal)
- **Secondary Background**: `#12121a` (Slightly lighter charcoal)
- **Primary Accent**: `#b829ff` (Neon Purple)
- **Secondary Accent**: `#9333ea` (Lighter purple)
- **Text Primary**: `#ffffff`
- **Text Secondary**: `#a1a1aa`
- **Glass Background**: `rgba(255, 255, 255, 0.05)`
- **Glass Border**: `rgba(255, 255, 255, 0.1)`

#### Typography
- **Font Family**: "Outfit" (Google Fonts)
- **Hero Title**: 4rem, bold, gradient text (white to neon purple)
- **Section Titles**: 2.5rem, bold
- **Body Text**: 1rem, regular
- **Navigation**: 0.9rem, medium, uppercase tracking

#### Spacing System
- Section padding: 100px vertical
- Card padding: 24px
- Element gaps: 16px, 24px, 32px

#### Visual Effects
- Glassmorphism: backdrop-blur(20px), semi-transparent background
- Neon glow: box-shadow with purple glow
- Smooth transitions: 0.3s ease-out default

### Components

#### Custom Cursor
- Size: 12px circle
- Color: Neon purple with glow
- Behavior: Follows mouse, scales to 1.5x on click
- Trail effect using CSS

#### Magnetic Navbar
- Logo on left, links on right
- Each link: subtle pull toward mouse cursor (translate within 30px radius)
- Links: Home, Projects, About, Contact
- Hover state: neon purple color

#### Hero Section
- Glassmorphism card: max-width 600px, centered
- Typing animation: "Developer & Creator" cycling through phrases
- Subtitle below typing text
- CTA button with glow effect

#### Project Cards
- 4 cards with placeholder projects
- Size: 320px width, 400px height
- 3D tilt effect on hover (perspective transform)
- Hidden "View Project" button reveals on hover
- Card content: image placeholder, title, description, tech stack tags

#### Particle Background
- Canvas element covering full viewport
- 50 particles floating
- Particles: small circles (2-4px), white with low opacity
- React to mouse: particles near cursor move away
- Subtle parallax effect

## 3. Functionality Specification

### Core Features
1. **Custom Cursor**
   - Hide default cursor
   - Render custom cursor element
   - Smooth follow with slight delay
   - Scale up on mousedown, scale down on mouseup

2. **Magnetic Navigation**
   - Track mouse position
   - Calculate distance to each nav link
   - Apply translate transform based on proximity (max 30px)
   - Smooth easing on movement

3. **Typing Animation**
   - Array of phrases: ["Developer & Creator", "UI/UX Designer", "Problem Solver", "Tech Enthusiast"]
   - Type out each letter, pause, delete, move to next
   - Blinking cursor at end

4. **3D Tilt Cards**
   - Track mouse position over card
   - Calculate rotation based on mouse offset from center
   - Max rotation: 15deg X and Y axis
   - Reset on mouse leave

5. **Particle System**
   - Initialize 50 particles with random positions
   - Each particle has velocity and opacity
   - Update position each frame
   - Boundary wrapping (reappear on opposite side)
   - Mouse repulsion: particles within 100px of cursor move away

### User Interactions
- Hover on nav links: magnetic pull effect
- Hover on cards: 3D tilt + reveal button
- Move mouse: cursor follows, particles react
- Click: cursor expands

### Edge Cases
- Mobile: disable custom cursor, disable magnetic effects
- Performance: use requestAnimationFrame for animations

## 4. Acceptance Criteria

### Visual Checkpoints
- [ ] Background is deep charcoal (#0a0a0f)
- [ ] Neon purple (#b829ff) used for accents and glows
- [ ] Glassmorphism card visible in hero with blur effect
- [ ] Custom cursor follows mouse smoothly
- [ ] Navigation links have magnetic pull effect
- [ ] Project cards tilt in 3D on hover
- [ ] "View Project" button appears on card hover
- [ ] Particles floating in background
- [ ] Particles react to mouse movement
- [ ] Typing animation cycles through phrases

### Functionality Checkpoints
- [ ] Page loads without errors
- [ ] All animations run at 60fps
- [ ] Responsive on mobile devices
- [ ] No console errors

## 5. Technical Implementation
- Single index.html file
- Tailwind CSS via CDN
- Framer Motion via CDN (for advanced animations)
- Vanilla JS for custom interactions
- Canvas API for particles