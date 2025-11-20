# HOTO Delivery Platform - Design System

Welcome to the HOTO Delivery Platform Design System. This comprehensive guide provides all the design specifications, component patterns, and implementation examples needed to build a consistent, professional, and accessible user interface.

## 📚 Documentation

### [UI Style Guide](./UI-STYLE-GUIDE.md)
The complete design specification covering:
- **Color Palette**: Primary, secondary, accent, functional, and background colors
- **Typography**: Font families, weights, sizes, and text styles
- **Component Styling**: Detailed specs for all UI components
- **Icons**: Lucide icon system and usage guidelines
- **Spacing System**: 4px-based spacing scale
- **Motion & Animation**: Timing, easing, and animation patterns
- **Dark Mode**: Complete dark mode color palette and adjustments
- **Accessibility**: Contrast ratios, focus indicators, and WCAG compliance

### [Component Examples](./COMPONENT-EXAMPLES.md)
Practical React + Tailwind CSS implementation examples for:
- Headers (Application, Section, Card)
- Sidebar Navigation
- Footers
- Tables (with sorting, filtering, empty states)
- Buttons (Primary, Secondary, Tertiary, Destructive, Icon)
- Toggle Switches
- Modals (Standard, Confirmation, Form, Full-screen)
- Hamburger Menu
- Charts (Bar, Pie, Line with color schemes)
- Forms (Inputs, Selects, Checkboxes, Radio, Textarea)
- Cards (Stat cards, Interactive cards)

## 🎨 Design Philosophy

The HOTO Delivery Platform design system is built on these core principles:

### Sharp Modernism
- Clean, crisp edges with minimal border radius
- Professional enterprise aesthetic
- Structured, grid-based layouts
- Inspired by C# WinForms clarity with modern web polish

### Monochrome Foundation
- Black, white, and grays form the visual base
- Strategic use of accent colors for actions and states
- High contrast for excellent readability
- Professional and timeless appearance

### Purposeful Motion
- Fast, snappy animations (150-300ms)
- Functional transitions that guide users
- Respects `prefers-reduced-motion`
- Never decorative, always purposeful

### Accessibility First
- WCAG 2.1 Level AA compliance minimum
- AAA contrast ratios where possible
- Keyboard navigation throughout
- Screen reader optimized
- Touch-friendly targets (44px minimum)

## 🚀 Quick Start

### 1. Install Dependencies

```bash
# Core dependencies
npm install lucide-react
npm install recharts

# Tailwind CSS (if not already installed)
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

### 2. Configure Tailwind

Update your `tailwind.config.js`:

```js
module.exports = {
  content: [
    "./src/**/*.{js,jsx,ts,tsx}",
  ],
  theme: {
    extend: {
      colors: {
        'primary-black': '#0F0F0F',
        'primary-gray': '#1A1A1A',
        'primary-white': '#FFFFFF',
        'accent-primary': '#3B82F6',
        'accent-secondary': '#06B6D4',
        'success': '#10B981',
        'warning': '#F59E0B',
        'error': '#EF4444',
        // Add more colors from the style guide
      },
      spacing: {
        '70': '280px', // Sidebar width
      },
      fontFamily: {
        sans: ['Inter', '-apple-system', 'BlinkMacSystemFont', 'sans-serif'],
      },
    },
  },
  plugins: [],
};
```

### 3. Add Global Styles

Create or update your global CSS file:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;

@layer base {
  body {
    @apply font-sans text-[#0F0F0F] bg-[#FAFAFA];
  }
}

/* Add animations from Component Examples */
@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

@keyframes scaleIn {
  from {
    opacity: 0;
    transform: scale(0.95);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}

/* Respect reduced motion */
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

### 4. Start Building

Browse the [Component Examples](./COMPONENT-EXAMPLES.md) and copy the code for the components you need. All examples are production-ready and follow the design specifications exactly.

## 📦 Component Library Structure

Recommended file structure for your component library:

```
src/
├── components/
│   ├── ui/
│   │   ├── buttons/
│   │   │   ├── PrimaryButton.jsx
│   │   │   ├── SecondaryButton.jsx
│   │   │   ├── IconButton.jsx
│   │   │   └── index.js
│   │   ├── cards/
│   │   │   ├── Card.jsx
│   │   │   ├── StatCard.jsx
│   │   │   └── index.js
│   │   ├── forms/
│   │   │   ├── Input.jsx
│   │   │   ├── Select.jsx
│   │   │   ├── Checkbox.jsx
│   │   │   ├── Radio.jsx
│   │   │   ├── ToggleSwitch.jsx
│   │   │   └── index.js
│   │   ├── navigation/
│   │   │   ├── Sidebar.jsx
│   │   │   ├── Header.jsx
│   │   │   ├── Footer.jsx
│   │   │   ├── HamburgerMenu.jsx
│   │   │   └── index.js
│   │   ├── modals/
│   │   │   ├── Modal.jsx
│   │   │   ├── ConfirmModal.jsx
│   │   │   └── index.js
│   │   ├── tables/
│   │   │   ├── DataTable.jsx
│   │   │   └── index.js
│   │   └── charts/
│   │       ├── BarChart.jsx
│   │       ├── PieChart.jsx
│   │       ├── LineChart.jsx
│   │       └── index.js
│   └── layouts/
│       ├── AppLayout.jsx
│       └── DashboardLayout.jsx
└── styles/
    └── globals.css
```

## 🎯 Key Components Overview

### Navigation
- **Sidebar**: 280px (expanded) / 64px (collapsed), dark background
- **Header**: 64px height, fixed top, dark background
- **Footer**: 56px height, dark background
- **Hamburger Menu**: Mobile-first slide-in panel

### Data Display
- **Tables**: Sortable, filterable, with hover states and selection
- **Cards**: Stat cards, content cards, interactive cards
- **Charts**: Bar, Pie, Line with coordinated color palettes

### Forms & Inputs
- **Inputs**: 44px height, rounded-md (6px), focus states
- **Buttons**: Primary, Secondary, Tertiary, Destructive variants
- **Toggles**: iOS-style switches with smooth animations
- **Checkboxes/Radio**: Custom styled, accessible

### Feedback
- **Modals**: Multiple sizes, with overlay and animations
- **Tooltips**: Dark background, white text, positioned dynamically
- **Alerts**: Success, Warning, Error, Info variants

## 🎨 Color Usage Guidelines

### When to Use Each Color

**Primary Colors (Black, White, Grays)**
- Use for 90% of the interface
- Backgrounds, text, borders, surfaces
- Creates professional, clean appearance

**Accent Primary (Blue #3B82F6)**
- Primary actions (Save, Submit, Confirm)
- Links and interactive elements
- Active states in navigation
- Primary chart series

**Accent Secondary (Cyan #06B6D4)**
- Secondary actions (Export, Download)
- Information highlights
- Secondary chart series

**Success (Green #10B981)**
- Success messages
- Completed states
- Positive metrics and trends

**Warning (Orange #F59E0B)**
- Warning messages
- Caution states
- Pending/attention required

**Error (Red #EF4444)**
- Error messages
- Destructive actions (Delete)
- Failed states
- Negative metrics

## 📏 Spacing Guidelines

Based on a 4px grid system:

- **4px (space-1)**: Tight groupings, icon gaps
- **8px (space-2)**: Small spacing, button groups
- **12px (space-3)**: Related elements
- **16px (space-4)**: Standard padding, element spacing
- **20px (space-5)**: Card padding, comfortable spacing
- **24px (space-6)**: Section spacing, component margins
- **32px (space-8)**: Large spacing, major sections
- **48px (space-12)**: Section separation, page margins

## 🔤 Typography Scale

**Headings:**
- H1: 32px / Bold - Page titles
- H2: 24px / Bold - Section headers
- H3: 20px / Semibold - Subsection headers
- H4: 16px / Semibold - Component headers

**Body:**
- Large: 18px / Regular - Important content
- Regular: 16px / Regular - Standard UI text
- Small: 14px / Regular - Supporting info

**Special:**
- Caption: 12px / Medium - Metadata, labels
- Button: 16px / Medium - All buttons
- Link: 16px / Medium - Clickable text

## 🌙 Dark Mode

The design system includes a complete dark mode palette. To implement:

1. Use CSS variables or Tailwind's dark mode
2. Swap colors according to the Dark Mode section in the style guide
3. Adjust accent colors for better contrast
4. Test all components in both modes

## ♿ Accessibility Checklist

- [ ] All interactive elements have focus indicators
- [ ] Touch targets are minimum 44px × 44px
- [ ] Color is not the only indicator of state
- [ ] Text contrast meets WCAG AA (AAA preferred)
- [ ] ARIA labels on all icons and interactive elements
- [ ] Keyboard navigation works throughout
- [ ] Screen reader tested
- [ ] Respects `prefers-reduced-motion`

## 📱 Responsive Breakpoints

- **Mobile**: < 768px
- **Tablet**: 768px - 1023px
- **Desktop**: ≥ 1024px
- **Large Desktop**: ≥ 1440px

Adjust layouts, spacing, and font sizes at each breakpoint (see style guide for details).

## 🛠️ Tools & Resources

### Design Tools
- **Figma**: For mockups and prototypes
- **Lucide Icons**: https://lucide.dev/
- **Tailwind CSS**: https://tailwindcss.com/

### Development Tools
- **React**: Component framework
- **Tailwind CSS**: Utility-first CSS
- **Recharts**: Chart library
- **Lucide React**: Icon library

### Testing Tools
- **Axe DevTools**: Accessibility testing
- **WAVE**: Web accessibility evaluation
- **Lighthouse**: Performance and accessibility audits

## 📝 Contributing

When adding new components to the design system:

1. **Follow the Style Guide**: All specifications must match exactly
2. **Document Your Component**: Add to Component Examples with code
3. **Ensure Accessibility**: Test with keyboard and screen readers
4. **Test Responsiveness**: Verify on mobile, tablet, desktop
5. **Consider Dark Mode**: Include dark mode styles
6. **Use Consistent Spacing**: Stick to the 4px grid system
7. **Update This README**: If adding new sections or patterns

## 🐛 Issues & Support

For questions, issues, or suggestions about the design system:
- Review the [UI Style Guide](./UI-STYLE-GUIDE.md) thoroughly
- Check [Component Examples](./COMPONENT-EXAMPLES.md) for implementation
- Consult the product design team for clarifications
- Open an issue in the project repository

## 📅 Version History

**v1.0.0** (2025-11-20)
- Initial release
- Complete design system specification
- All core components documented
- Dark mode support
- Accessibility guidelines
- Responsive design specifications

## 🔗 Quick Links

- [UI Style Guide](./UI-STYLE-GUIDE.md) - Complete design specifications
- [Component Examples](./COMPONENT-EXAMPLES.md) - Code implementation examples
- [Lucide Icons](https://lucide.dev/) - Icon library reference
- [Tailwind CSS Docs](https://tailwindcss.com/docs) - Utility class reference

---

**Built with precision for the HOTO Delivery Platform**

*Last updated: 2025-11-20*
