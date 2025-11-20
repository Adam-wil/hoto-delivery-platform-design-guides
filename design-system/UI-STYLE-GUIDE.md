# HOTO Delivery Platform - UI Style Guide

## Overview
This style guide defines the visual language for the HOTO Delivery Platform. The design philosophy embraces **sharp, clean modernism** inspired by professional enterprise applications, combining the structured clarity of WinForms with contemporary web design principles.

### Design Principles
- **Bold Simplicity**: Clean, sharp interfaces with minimal decoration
- **Professional Clarity**: Enterprise-grade visual hierarchy
- **Monochrome Foundation**: Black, white, and grays form the base palette
- **Strategic Color**: Accent colors used purposefully for actions and states
- **Breathable Space**: Generous whitespace for cognitive comfort
- **Sharp Geometry**: Minimal border radius, crisp edges, structured layouts

---

## Color Palette

### Primary Colors
- **Primary White** - `#FFFFFF`
  - Usage: Card backgrounds, modals, clean surfaces
  - Application: Primary content containers

- **Primary Black** - `#0F0F0F`
  - Usage: Primary text, headers, high-emphasis content
  - Application: Main text, navigation labels, titles

- **Primary Gray** - `#1A1A1A`
  - Usage: Sidebar backgrounds, headers, footers
  - Application: Navigation containers, application chrome

### Secondary Colors
- **Secondary Gray Light** - `#F5F5F5`
  - Usage: Page backgrounds, hover states on white surfaces
  - Application: Main app background, subtle highlights

- **Secondary Gray Medium** - `#E5E5E5`
  - Usage: Borders, dividers, table separators
  - Application: Visual separation, grid lines

- **Secondary Gray Dark** - `#2D2D2D`
  - Usage: Secondary containers, dark surface variations
  - Application: Elevated panels, secondary navigation

### Accent Colors
- **Accent Primary** - `#3B82F6` (Professional Blue)
  - Usage: Primary actions, interactive elements, links
  - Application: Primary buttons, active states, charts (primary)

- **Accent Secondary** - `#06B6D4` (Cyan)
  - Usage: Secondary actions, information highlights
  - Application: Secondary buttons, info badges, charts (secondary)

- **Accent Tertiary** - `#8B5CF6` (Purple)
  - Usage: Tertiary visual interest, chart variety
  - Application: Charts (tertiary), special highlights

### Functional Colors
- **Success Green** - `#10B981`
  - Usage: Success states, confirmations, positive metrics
  - Application: Success messages, completed states, up-trending charts

- **Warning Orange** - `#F59E0B`
  - Usage: Warnings, cautions, attention required
  - Application: Warning messages, pending states

- **Error Red** - `#EF4444`
  - Usage: Errors, destructive actions, critical alerts
  - Application: Error messages, delete actions, down-trending charts

- **Info Blue** - `#0EA5E9`
  - Usage: Informational messages, helpful tips
  - Application: Info banners, tooltips

### Background Colors
- **Background Primary** - `#FAFAFA`
  - Usage: Main application background
  - Application: Body background, layout base

- **Background Secondary** - `#FFFFFF`
  - Usage: Content cards, modals, elevated surfaces
  - Application: All primary content containers

- **Background Dark** - `#1A1A1A`
  - Usage: Headers, sidebars, footers
  - Application: Navigation chrome, application frame

- **Background Overlay** - `rgba(15, 15, 15, 0.6)`
  - Usage: Modal backdrops, overlays
  - Application: Behind modals and dialogs

### Text Colors
- **Text Primary** - `#0F0F0F`
  - Usage: Primary content, headings, important text
  - Contrast: AAA on white backgrounds

- **Text Secondary** - `#525252`
  - Usage: Secondary content, supporting information
  - Contrast: AA on white backgrounds

- **Text Tertiary** - `#737373`
  - Usage: Placeholder text, disabled states, timestamps
  - Contrast: Minimum AA on white backgrounds

- **Text Inverse** - `#FFFFFF`
  - Usage: Text on dark backgrounds
  - Application: Sidebar labels, footer text, dark buttons

### Chart Color Schemes

#### Primary Chart Palette (Sequential Data)
1. **Chart Primary** - `#3B82F6` (Blue)
2. **Chart Secondary** - `#06B6D4` (Cyan)
3. **Chart Tertiary** - `#8B5CF6` (Purple)
4. **Chart Quaternary** - `#10B981` (Green)
5. **Chart Quinary** - `#F59E0B` (Orange)
6. **Chart Senary** - `#EC4899` (Pink)

#### Pie Chart Palette
- **Segment 1** - `#3B82F6` (Blue) - Primary/largest segment
- **Segment 2** - `#06B6D4` (Cyan) - Secondary segment
- **Segment 3** - `#10B981` (Green) - Tertiary segment
- **Segment 4** - `#8B5CF6` (Purple) - Quaternary segment
- **Segment 5** - `#F59E0B` (Orange) - Quinary segment
- **Segment 6** - `#EF4444` (Red) - Additional segment
- **Segment 7** - `#EC4899` (Pink) - Additional segment
- **Segment 8** - `#6366F1` (Indigo) - Additional segment

#### Bar Chart Palette
- **Primary Series** - `#3B82F6` (Blue)
- **Secondary Series** - `#10B981` (Green)
- **Tertiary Series** - `#F59E0B` (Orange)
- **Comparison Baseline** - `#E5E5E5` (Light Gray)
- **Negative Values** - `#EF4444` (Red)
- **Positive Values** - `#10B981` (Green)

#### Line Chart Palette
- **Line 1** - `#3B82F6` (Blue)
- **Line 2** - `#10B981` (Green)
- **Line 3** - `#8B5CF6` (Purple)
- **Line 4** - `#F59E0B` (Orange)
- **Gridlines** - `#E5E5E5` (Light Gray)
- **Axis** - `#A3A3A3` (Medium Gray)

---

## Typography

### Font Family
**Primary Font**: `Inter, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif`
- Modern, professional, highly legible
- Excellent for UI and data display
- Clean geometric forms align with sharp aesthetic

**Monospace Font**: `'JetBrains Mono', 'Fira Code', 'Courier New', monospace`
- Used for code, IDs, technical data
- Clear distinction for technical content

### Font Weights
- **Regular**: 400 - Body text, standard content
- **Medium**: 500 - Emphasis, subheadings
- **Semibold**: 600 - Section headers, card titles
- **Bold**: 700 - Page titles, major headers

### Text Styles

#### Headings
**H1 - Page Title**
- Size: `32px` / Line Height: `40px`
- Weight: Bold (700)
- Letter Spacing: `-0.5px`
- Color: Text Primary (#0F0F0F)
- Usage: Main page titles, primary headers

**H2 - Section Header**
- Size: `24px` / Line Height: `32px`
- Weight: Bold (700)
- Letter Spacing: `-0.3px`
- Color: Text Primary (#0F0F0F)
- Usage: Major section headers, card titles

**H3 - Subsection Header**
- Size: `20px` / Line Height: `28px`
- Weight: Semibold (600)
- Letter Spacing: `-0.2px`
- Color: Text Primary (#0F0F0F)
- Usage: Subsections, grouped content headers

**H4 - Component Header**
- Size: `16px` / Line Height: `24px`
- Weight: Semibold (600)
- Letter Spacing: `0px`
- Color: Text Primary (#0F0F0F)
- Usage: Table headers, small component titles

#### Body Text
**Body Large**
- Size: `18px` / Line Height: `28px`
- Weight: Regular (400)
- Letter Spacing: `0px`
- Color: Text Primary (#0F0F0F)
- Usage: Primary reading content, important information

**Body Regular**
- Size: `16px` / Line Height: `24px`
- Weight: Regular (400)
- Letter Spacing: `0px`
- Color: Text Primary (#0F0F0F)
- Usage: Standard UI text, form labels, table content

**Body Small**
- Size: `14px` / Line Height: `20px`
- Weight: Regular (400)
- Letter Spacing: `0.1px`
- Color: Text Secondary (#525252)
- Usage: Supporting information, descriptions

#### Special Text
**Caption**
- Size: `12px` / Line Height: `16px`
- Weight: Medium (500)
- Letter Spacing: `0.2px`
- Color: Text Tertiary (#737373)
- Usage: Timestamps, metadata, helper text

**Label**
- Size: `14px` / Line Height: `20px`
- Weight: Medium (500)
- Letter Spacing: `0.1px`
- Color: Text Secondary (#525252)
- Usage: Form labels, filter labels, tags

**Button Text**
- Size: `16px` / Line Height: `24px`
- Weight: Medium (500)
- Letter Spacing: `0.1px`
- Usage: All button labels

**Link Text**
- Size: `16px` / Line Height: `24px`
- Weight: Medium (500)
- Letter Spacing: `0px`
- Color: Accent Primary (#3B82F6)
- Text Decoration: None (underline on hover)
- Usage: Clickable links, navigation

**Code/Monospace**
- Size: `14px` / Line Height: `20px`
- Weight: Regular (400)
- Font Family: Monospace
- Background: `#F5F5F5`
- Padding: `2px 6px`
- Border Radius: `4px`
- Usage: IDs, technical values, code snippets

---

## Component Styling

### Headers

#### Main Application Header
- **Height**: `64px`
- **Background**: Primary Gray (#1A1A1A)
- **Border Bottom**: `1px solid #2D2D2D`
- **Padding**: `0 24px`
- **Shadow**: None (sharp, flat design)
- **Content Alignment**: Flex, space-between
- **Logo/Title Color**: Text Inverse (#FFFFFF)
- **Logo Size**: `32px` height
- **Icon Size**: `24px`
- **Icon Color**: Text Inverse (#FFFFFF)

#### Section Header
- **Height**: `56px`
- **Background**: Background Secondary (#FFFFFF)
- **Border Bottom**: `1px solid #E5E5E5`
- **Padding**: `16px 24px`
- **Title**: H2 style
- **Action Buttons**: Right-aligned, 8px spacing

#### Card Header
- **Padding**: `16px 20px`
- **Background**: Background Secondary (#FFFFFF)
- **Border Bottom**: `1px solid #E5E5E5`
- **Title**: H3 style
- **Actions**: Right-aligned icon buttons (20px)

### Sidebar Navigation

#### Primary Sidebar
- **Width**: `280px` (expanded) / `64px` (collapsed)
- **Background**: Primary Gray (#1A1A1A)
- **Border Right**: `1px solid #2D2D2D`
- **Padding**: `24px 0`
- **Transition**: `width 250ms ease-out`

#### Navigation Item
- **Height**: `48px`
- **Padding**: `12px 20px` (expanded) / `12px` (collapsed)
- **Margin**: `0 12px 4px 12px`
- **Border Radius**: `6px`
- **Icon Size**: `24px`
- **Icon Color**: `#A3A3A3` (inactive) / `#FFFFFF` (active)
- **Text Color**: `#D4D4D4` (inactive) / `#FFFFFF` (active)
- **Text Size**: `15px`, Weight: Medium (500)
- **Gap**: `12px` between icon and text

**States:**
- **Default**: Background transparent, icon/text gray
- **Hover**: Background `rgba(255, 255, 255, 0.08)`, icon/text lighter
- **Active**: Background `rgba(59, 130, 246, 0.15)`, icon/text `#60A5FA` (blue tint)
- **Focus**: `2px solid #3B82F6` outline, `2px` offset

#### Sidebar Header
- **Padding**: `0 20px 24px 20px`
- **Border Bottom**: `1px solid #2D2D2D`
- **Margin Bottom**: `16px`
- **Logo**: `40px` height
- **Title**: `18px`, Bold, Text Inverse

#### Sidebar Footer
- **Padding**: `16px 20px`
- **Border Top**: `1px solid #2D2D2D`
- **Margin Top**: `auto`
- **User Avatar**: `36px` circle
- **User Name**: `14px`, Medium, Text Inverse
- **User Role**: `12px`, Regular, `#A3A3A3`

### Footers

#### Application Footer
- **Height**: `56px`
- **Background**: Primary Gray (#1A1A1A)
- **Border Top**: `1px solid #2D2D2D`
- **Padding**: `16px 24px`
- **Text Color**: `#D4D4D4`
- **Text Size**: `14px`
- **Link Color**: `#A3A3A3`
- **Link Hover**: `#FFFFFF`
- **Content**: Copyright, version, links (right-aligned)

#### Card Footer
- **Padding**: `16px 20px`
- **Background**: Background Secondary (#FFFFFF)
- **Border Top**: `1px solid #E5E5E5`
- **Actions**: Right-aligned buttons with `8px` spacing
- **Metadata**: Left-aligned, Caption style, Text Tertiary

### Tables

#### Table Container
- **Background**: Background Secondary (#FFFFFF)
- **Border**: `1px solid #E5E5E5`
- **Border Radius**: `8px`
- **Shadow**: `0 1px 3px rgba(0, 0, 0, 0.05)`
- **Overflow**: Hidden

#### Table Header
- **Background**: `#F9FAFB`
- **Border Bottom**: `1px solid #E5E5E5`
- **Height**: `48px`
- **Padding**: `12px 16px`
- **Text**: `14px`, Semibold (600), Text Primary, Uppercase `0.5px` tracking
- **Sticky**: Top position when scrolling

#### Table Row
- **Height**: `56px`
- **Padding**: `16px`
- **Border Bottom**: `1px solid #F5F5F5`
- **Text**: Body Regular, Text Primary

**States:**
- **Default**: Background white
- **Hover**: Background `#FAFAFA`
- **Selected**: Background `#EFF6FF`, left border `3px solid #3B82F6`
- **Focus**: Outline `2px solid #3B82F6`, offset `2px`

#### Table Cell
- **Padding**: `16px`
- **Alignment**: Left (text), Right (numbers), Center (actions)
- **Text**: `15px`, Regular (400)
- **Number Format**: Monospace font for consistency

#### Table Actions
- **Icon Buttons**: `20px` icons, `8px` spacing
- **Icon Color**: `#737373` (hover: `#0F0F0F`)
- **Hover**: Background `#F5F5F5`, `border-radius: 4px`

#### Empty State
- **Padding**: `48px 24px`
- **Text Alignment**: Center
- **Icon**: `48px`, `#D4D4D4`
- **Message**: Body Regular, Text Secondary
- **Action**: Secondary Button

### Buttons

#### Primary Button
- **Background**: Accent Primary (#3B82F6)
- **Text**: Text Inverse (#FFFFFF), Button Text style
- **Height**: `44px`
- **Padding**: `12px 24px`
- **Border Radius**: `6px`
- **Border**: None
- **Shadow**: `0 1px 2px rgba(0, 0, 0, 0.05)`
- **Transition**: `all 150ms ease-out`

**States:**
- **Hover**: Background `#2563EB`, shadow `0 2px 4px rgba(0, 0, 0, 0.1)`
- **Active**: Background `#1D4ED8`, shadow `inset 0 2px 4px rgba(0, 0, 0, 0.1)`
- **Focus**: Outline `2px solid #93C5FD`, offset `2px`
- **Disabled**: Background `#E5E5E5`, text `#A3A3A3`, cursor `not-allowed`

#### Secondary Button
- **Background**: Transparent
- **Text**: Accent Primary (#3B82F6), Button Text style
- **Height**: `44px`
- **Padding**: `12px 24px`
- **Border Radius**: `6px`
- **Border**: `1.5px solid #3B82F6`
- **Transition**: `all 150ms ease-out`

**States:**
- **Hover**: Background `#EFF6FF`, border `#2563EB`
- **Active**: Background `#DBEAFE`, border `#1D4ED8`
- **Focus**: Outline `2px solid #93C5FD`, offset `2px`
- **Disabled**: Border `#E5E5E5`, text `#A3A3A3`, cursor `not-allowed`

#### Tertiary Button (Ghost)
- **Background**: Transparent
- **Text**: Text Primary (#0F0F0F), Button Text style
- **Height**: `44px`
- **Padding**: `12px 24px`
- **Border Radius**: `6px`
- **Border**: None

**States:**
- **Hover**: Background `#F5F5F5`
- **Active**: Background `#E5E5E5`
- **Focus**: Outline `2px solid #3B82F6`, offset `2px`
- **Disabled**: Text `#A3A3A3`, cursor `not-allowed`

#### Destructive Button
- **Background**: Error Red (#EF4444)
- **Text**: Text Inverse (#FFFFFF), Button Text style
- **Height**: `44px`
- **Padding**: `12px 24px`
- **Border Radius**: `6px`
- **Border**: None
- **Shadow**: `0 1px 2px rgba(0, 0, 0, 0.05)`

**States:**
- **Hover**: Background `#DC2626`
- **Active**: Background `#B91C1C`
- **Focus**: Outline `2px solid #FCA5A5`, offset `2px`

#### Icon Button
- **Size**: `40px` × `40px`
- **Icon Size**: `20px`
- **Icon Color**: `#525252`
- **Background**: Transparent
- **Border Radius**: `6px`
- **Padding**: `10px`

**States:**
- **Hover**: Background `#F5F5F5`, icon color `#0F0F0F`
- **Active**: Background `#E5E5E5`
- **Focus**: Outline `2px solid #3B82F6`, offset `2px`

#### Button Group
- **Gap**: `8px` between buttons
- **Alignment**: Horizontal flex
- **Primary Action**: Always rightmost position

### Cards

#### Standard Card
- **Background**: Background Secondary (#FFFFFF)
- **Border**: `1px solid #E5E5E5`
- **Border Radius**: `8px`
- **Padding**: `20px`
- **Shadow**: `0 1px 3px rgba(0, 0, 0, 0.05)`
- **Transition**: `shadow 200ms ease-out`

**Hover State:**
- **Shadow**: `0 4px 6px rgba(0, 0, 0, 0.07)`

#### Elevated Card
- **Background**: Background Secondary (#FFFFFF)
- **Border**: None
- **Border Radius**: `8px`
- **Padding**: `20px`
- **Shadow**: `0 4px 6px rgba(0, 0, 0, 0.07)`

#### Interactive Card
- **Cursor**: Pointer
- **Transition**: `all 200ms ease-out`

**States:**
- **Hover**: Shadow `0 6px 12px rgba(0, 0, 0, 0.1)`, transform `translateY(-2px)`
- **Active**: Shadow `0 2px 4px rgba(0, 0, 0, 0.06)`, transform `translateY(0)`
- **Focus**: Outline `2px solid #3B82F6`, offset `2px`

#### Stat Card
- **Layout**: Vertical, centered
- **Icon**: `48px`, Accent Primary circle background (light tint)
- **Value**: `32px`, Bold, Text Primary
- **Label**: Caption style, Text Secondary
- **Gap**: `12px` between elements

### Input Fields

#### Text Input
- **Height**: `44px`
- **Padding**: `12px 16px`
- **Background**: Background Secondary (#FFFFFF)
- **Border**: `1px solid #D4D4D4`
- **Border Radius**: `6px`
- **Text**: Body Regular, Text Primary
- **Placeholder**: Text Tertiary (#737373)
- **Transition**: `border 150ms ease-out`

**States:**
- **Focus**: Border `2px solid #3B82F6`, padding adjust to compensate
- **Error**: Border `2px solid #EF4444`
- **Success**: Border `2px solid #10B981`
- **Disabled**: Background `#F5F5F5`, text `#A3A3A3`, cursor `not-allowed`

#### Textarea
- **Min Height**: `120px`
- **Padding**: `12px 16px`
- **Resize**: Vertical only
- **All other properties**: Same as Text Input

#### Select Dropdown
- **Height**: `44px`
- **Padding**: `12px 16px`
- **Background**: Background Secondary (#FFFFFF)
- **Border**: `1px solid #D4D4D4`
- **Border Radius**: `6px`
- **Icon**: Chevron-down, `20px`, right `12px`
- **Dropdown Max Height**: `320px`
- **Dropdown Shadow**: `0 4px 12px rgba(0, 0, 0, 0.15)`
- **Dropdown Border**: `1px solid #E5E5E5`
- **Option Height**: `40px`
- **Option Padding**: `12px 16px`
- **Option Hover**: Background `#F5F5F5`
- **Option Selected**: Background `#EFF6FF`, text Accent Primary

#### Checkbox
- **Size**: `20px` × `20px`
- **Border**: `2px solid #D4D4D4`
- **Border Radius**: `4px`
- **Background**: Background Secondary (#FFFFFF)
- **Checkmark**: Lucide Check icon, `16px`, Text Inverse

**States:**
- **Checked**: Background Accent Primary, border Accent Primary
- **Hover**: Border `#A3A3A3`
- **Focus**: Outline `2px solid #93C5FD`, offset `2px`
- **Disabled**: Background `#F5F5F5`, border `#E5E5E5`

#### Radio Button
- **Size**: `20px` × `20px`
- **Border**: `2px solid #D4D4D4`
- **Border Radius**: `50%` (circle)
- **Background**: Background Secondary (#FFFFFF)
- **Indicator**: `10px` circle, Accent Primary

**States:**
- **Selected**: Border Accent Primary, inner circle visible
- **Hover**: Border `#A3A3A3`
- **Focus**: Outline `2px solid #93C5FD`, offset `2px`
- **Disabled**: Background `#F5F5F5`, border `#E5E5E5`

#### Toggle Switch

**Container:**
- **Width**: `48px`
- **Height**: `24px`
- **Border Radius**: `12px` (pill shape)
- **Background**: `#D4D4D4` (off) / Accent Primary (#3B82F6) (on)
- **Transition**: `background 200ms ease-out`
- **Cursor**: Pointer

**Toggle Thumb:**
- **Size**: `20px` × `20px`
- **Border Radius**: `50%` (circle)
- **Background**: Background Secondary (#FFFFFF)
- **Shadow**: `0 2px 4px rgba(0, 0, 0, 0.2)`
- **Position**: `2px` from left (off) / `26px` from left (on)
- **Transition**: `transform 200ms ease-out`

**States:**
- **Off**: Background `#D4D4D4`, thumb left
- **On**: Background Accent Primary, thumb right
- **Hover (off)**: Background `#A3A3A3`
- **Hover (on)**: Background `#2563EB`
- **Focus**: Outline `2px solid #93C5FD`, offset `2px`
- **Disabled**: Background `#E5E5E5`, cursor `not-allowed`

**With Label:**
- **Gap**: `12px` between toggle and label
- **Label**: Body Regular, Text Primary
- **Layout**: Horizontal flex, align center

### Modals

#### Modal Overlay
- **Background**: Background Overlay (rgba(15, 15, 15, 0.6))
- **Position**: Fixed, full screen
- **Z-Index**: 1000
- **Backdrop Blur**: `4px` (modern browsers)
- **Animation**: Fade in `200ms ease-out`

#### Modal Container
- **Background**: Background Secondary (#FFFFFF)
- **Border Radius**: `8px`
- **Shadow**: `0 20px 25px -5px rgba(0, 0, 0, 0.3)`
- **Max Width**: `600px` (default) / `900px` (large) / `400px` (small)
- **Max Height**: `90vh`
- **Margin**: Auto center
- **Position**: Fixed, centered
- **Z-Index**: 1001
- **Animation**: Scale up from 95% + fade in, `250ms ease-out`

#### Modal Header
- **Padding**: `24px 24px 16px 24px`
- **Border Bottom**: `1px solid #E5E5E5`
- **Title**: H2 style
- **Close Button**: Top-right, icon button, `24px` icon (X)
- **Close Button Position**: Absolute `16px` top, `16px` right

#### Modal Body
- **Padding**: `24px`
- **Max Height**: `60vh`
- **Overflow**: Auto scroll
- **Text**: Body Regular

#### Modal Footer
- **Padding**: `16px 24px 24px 24px`
- **Border Top**: `1px solid #E5E5E5`
- **Actions**: Right-aligned, `8px` gap
- **Primary Action**: Rightmost position

#### Modal Variants

**Confirmation Modal:**
- **Icon**: Warning/Question icon, `48px`, top center
- **Title**: Centered, H2
- **Message**: Centered, Body Regular
- **Actions**: Centered, Primary + Secondary buttons

**Form Modal:**
- **Layout**: Standard header/body/footer
- **Form Spacing**: `20px` between fields
- **Labels**: Above inputs

**Full-Screen Modal:**
- **Width**: `100vw`
- **Height**: `100vh`
- **Border Radius**: `0`
- **Header**: Application header style
- **Body**: Full width, scrollable

### Hamburger Menu

#### Hamburger Button
- **Size**: `40px` × `40px`
- **Background**: Transparent
- **Border**: None
- **Border Radius**: `6px`
- **Padding**: `8px`
- **Position**: Usually top-left or top-right

**Icon Construction (3 lines):**
- **Line Width**: `24px`
- **Line Height**: `2px`
- **Line Color**: Text Primary (#0F0F0F) or Text Inverse (#FFFFFF)
- **Gap**: `6px` between lines
- **Border Radius**: `1px` (pill-shaped lines)
- **Transition**: `all 250ms ease-out`

**States:**
- **Hover**: Background `#F5F5F5`, lines slightly expand
- **Active (Menu Open)**:
  - Top line: Rotate `45deg`, move to center
  - Middle line: Opacity `0`
  - Bottom line: Rotate `-45deg`, move to center
  - Forms an X shape

#### Mobile Menu Panel
- **Width**: `280px` (slide-in) or `100vw` (full-width)
- **Height**: `100vh`
- **Background**: Primary Gray (#1A1A1A)
- **Position**: Fixed, right or left
- **Z-Index**: 999
- **Shadow**: `0 0 20px rgba(0, 0, 0, 0.5)`
- **Animation**: Slide in from side, `300ms ease-out`
- **Overlay**: Same as Modal Overlay

**Menu Items:**
- Same styling as Sidebar Navigation Items
- **Padding**: `16px 20px`
- **Gap**: `4px` between items

### Charts

#### Chart Container
- **Background**: Background Secondary (#FFFFFF)
- **Border**: `1px solid #E5E5E5`
- **Border Radius**: `8px`
- **Padding**: `24px`
- **Shadow**: `0 1px 3px rgba(0, 0, 0, 0.05)`

#### Chart Title
- **Style**: H3
- **Margin Bottom**: `20px`
- **Alignment**: Left

#### Chart Legend
- **Position**: Top-right or bottom-center
- **Item Gap**: `16px`
- **Indicator**: `12px` × `12px` rounded square or circle
- **Label**: `14px`, Medium, Text Secondary
- **Layout**: Horizontal flex

#### Axis Styling
- **Axis Lines**: `1px solid #E5E5E5`
- **Tick Marks**: `1px solid #E5E5E5`, `4px` length
- **Tick Labels**: Caption style, Text Tertiary
- **Grid Lines**: `1px solid #F5F5F5`, dashed `4px 4px`

#### Tooltips
- **Background**: Primary Black (#0F0F0F)
- **Text**: `13px`, Medium, Text Inverse
- **Padding**: `8px 12px`
- **Border Radius**: `6px`
- **Shadow**: `0 4px 6px rgba(0, 0, 0, 0.2)`
- **Arrow**: `6px` triangle, same background color
- **Max Width**: `240px`

#### Pie Chart Specific
- **Stroke**: `2px solid #FFFFFF` between segments
- **Hover**: Segment expands by `4px`, shadow `0 2px 8px rgba(0, 0, 0, 0.15)`
- **Label Position**: Outside segments with connector lines
- **Connector Line**: `1px solid #D4D4D4`
- **Label**: `13px`, Medium, Text Primary
- **Percentage**: `12px`, Regular, Text Secondary

#### Bar Chart Specific
- **Bar Corner Radius**: `4px` (top corners only)
- **Bar Gap**: `8px` between bars
- **Group Gap**: `24px` between groups
- **Min Bar Width**: `24px`
- **Max Bar Width**: `64px`
- **Hover**: Opacity `0.8`, cursor pointer
- **Zero Baseline**: `2px solid #A3A3A3`

#### Line Chart Specific
- **Line Width**: `2px`
- **Point Radius**: `4px`
- **Point Stroke**: `2px solid #FFFFFF`
- **Point Hover**: Radius `6px`, shadow `0 2px 4px rgba(0, 0, 0, 0.2)`
- **Area Fill**: Linear gradient, color to transparent (20% opacity to 0%)
- **Smooth Curves**: Bezier curves (tension: 0.4)

---

## Icons

### Icon System: Lucide React
**Library**: [Lucide Icons](https://lucide.dev/)
- Clean, consistent line-based icon set
- Perfect for sharp, modern aesthetic
- Highly customizable stroke width and size

### Icon Sizes
- **Extra Small**: `16px` - Inline with text, badges
- **Small**: `20px` - Table actions, small buttons
- **Medium**: `24px` - Standard UI icons, navigation
- **Large**: `32px` - Feature highlights, empty states
- **Extra Large**: `48px` - Hero sections, large empty states

### Icon Styling
- **Stroke Width**: `2px` (standard) / `1.5px` (delicate) / `2.5px` (bold)
- **Color**: Inherit from parent or explicit color
- **Line Cap**: Round
- **Line Join**: Round

### Icon Usage

#### Navigation Icons
- **Size**: `24px`
- **Stroke**: `2px`
- **Color**: `#A3A3A3` (inactive) / `#FFFFFF` (active) / `#60A5FA` (active with accent)
- **Examples**: Menu, Home, Settings, User, Package, TruckIcon

#### Action Icons
- **Size**: `20px`
- **Stroke**: `2px`
- **Color**: `#525252` (default) / `#0F0F0F` (hover)
- **Examples**: Edit, Trash, Eye, Copy, Download, Upload, Plus, X

#### Status Icons
- **Size**: `20px`
- **Stroke**: `2px`
- **Success**: CheckCircle, `#10B981`
- **Warning**: AlertTriangle, `#F59E0B`
- **Error**: XCircle, `#EF4444`
- **Info**: Info, `#0EA5E9`

#### Chart Icons
- **Size**: `24px`
- **Stroke**: `2px`
- **Color**: Text Tertiary
- **Examples**: BarChart, PieChart, LineChart, TrendingUp, TrendingDown

#### Common Icons List
- **Menu**: Menu (hamburger)
- **Close**: X
- **Add**: Plus
- **Edit**: Edit / Pencil
- **Delete**: Trash / Trash2
- **Search**: Search
- **Filter**: Filter
- **Settings**: Settings
- **User**: User / UserCircle
- **Notifications**: Bell
- **Home**: Home
- **Dashboard**: LayoutDashboard
- **Orders**: Package / ShoppingCart
- **Deliveries**: Truck
- **Calendar**: Calendar
- **Clock**: Clock
- **Location**: MapPin
- **Upload**: Upload
- **Download**: Download
- **Export**: FileDown
- **Import**: FileUp
- **More**: MoreVertical / MoreHorizontal
- **Chevrons**: ChevronDown, ChevronUp, ChevronLeft, ChevronRight
- **Arrows**: ArrowLeft, ArrowRight, ArrowUp, ArrowDown
- **Check**: Check / CheckCircle
- **Alert**: AlertCircle / AlertTriangle
- **Info**: Info
- **Help**: HelpCircle

---

## Spacing System

### Base Unit: 4px

All spacing follows a `4px` base unit for consistency and pixel-perfect alignment.

### Spacing Scale
- **Space 0**: `0px` - No spacing
- **Space 1**: `4px` - Micro spacing, tight groupings
- **Space 2**: `8px` - Small spacing, icon gaps, button groups
- **Space 3**: `12px` - Default gap, related elements
- **Space 4**: `16px` - Standard padding, element spacing
- **Space 5**: `20px` - Card padding, comfortable spacing
- **Space 6**: `24px` - Section spacing, component margins
- **Space 8**: `32px` - Large spacing, major sections
- **Space 10**: `40px` - Extra large spacing
- **Space 12**: `48px` - Section separation, page margins
- **Space 16**: `64px` - Major layout spacing
- **Space 20**: `80px` - Page-level spacing

### Application Guidelines

#### Component Internal Spacing
- **Buttons**: `12px` vertical, `24px` horizontal
- **Cards**: `20px` all sides
- **Modals**: `24px` all sides
- **Tables**: `16px` cell padding
- **Forms**: `16px` between fields

#### Layout Spacing
- **Page Margins**: `24px` (mobile) / `32px` (tablet) / `48px` (desktop)
- **Section Gaps**: `32px` (mobile) / `48px` (desktop)
- **Grid Gaps**: `16px` (mobile) / `24px` (desktop)
- **Card Grids**: `20px` gap

#### Element Spacing
- **Icon + Text**: `8px` gap
- **Button Groups**: `8px` gap
- **Form Label + Input**: `8px` gap
- **Heading + Content**: `12px` gap
- **Paragraph Spacing**: `16px` between paragraphs

---

## Motion & Animation

### Principles
- **Purposeful**: Every animation serves a function
- **Snappy**: Quick, responsive, never sluggish
- **Subtle**: Professional, not distracting
- **Consistent**: Same duration/easing for similar actions

### Timing

#### Micro Interactions
- **Duration**: `150ms`
- **Easing**: `ease-out`
- **Usage**: Button hovers, icon state changes, input focus

#### Standard Transitions
- **Duration**: `200ms`
- **Easing**: `ease-out`
- **Usage**: Dropdown opening, card hover, color changes

#### Medium Transitions
- **Duration**: `250ms`
- **Easing**: `ease-out`
- **Usage**: Modal appearance, sidebar toggle, menu slide

#### Emphasis Transitions
- **Duration**: `300ms`
- **Easing**: `ease-in-out`
- **Usage**: Page transitions, large component changes

### Easing Functions

**Ease Out** - `cubic-bezier(0, 0, 0.2, 1)`
- Default for most interactions
- Starts fast, ends slow
- Feels responsive and natural

**Ease In Out** - `cubic-bezier(0.4, 0, 0.2, 1)`
- Smooth both ways
- Used for reversible animations

**Sharp** - `cubic-bezier(0.4, 0, 0.6, 1)`
- Quick, decisive
- Used for dismissing elements

### Animation Patterns

#### Fade In/Out
- **Property**: `opacity`
- **Duration**: `200ms`
- **Easing**: `ease-out`
- **From/To**: `0` to `1` (in) / `1` to `0` (out)

#### Slide In/Out
- **Property**: `transform: translateX()` or `translateY()`
- **Duration**: `250ms`
- **Easing**: `ease-out`
- **Distance**: `24px` or `100%`
- **Combine**: With fade for polish

#### Scale
- **Property**: `transform: scale()`
- **Duration**: `200ms`
- **Easing**: `ease-out`
- **From/To**: `0.95` to `1` (grow) / `1` to `0.95` (shrink)
- **Combine**: With fade for modals

#### Expand/Collapse
- **Property**: `max-height` + `opacity`
- **Duration**: `250ms`
- **Easing**: `ease-in-out`
- **Usage**: Accordions, dropdowns

#### Loading Spinner
- **Animation**: Rotate `360deg`
- **Duration**: `1000ms`
- **Easing**: `linear`
- **Iteration**: Infinite
- **Icon**: Loader / Loader2 from Lucide

#### Skeleton Loading
- **Animation**: Shimmer gradient moving left to right
- **Duration**: `1500ms`
- **Easing**: `ease-in-out`
- **Iteration**: Infinite
- **Gradient**: `#F5F5F5` to `#E5E5E5` to `#F5F5F5`

### Reduced Motion
**Respect user preferences**: `prefers-reduced-motion: reduce`
- Disable all animations
- Use instant state changes
- Maintain functionality without motion

---

## Dark Mode

### Background Colors
- **Background Primary**: `#0F0F0F`
- **Background Secondary**: `#1A1A1A`
- **Background Tertiary**: `#2D2D2D`
- **Background Elevated**: `#262626`

### Text Colors
- **Text Primary**: `#FAFAFA`
- **Text Secondary**: `#D4D4D4`
- **Text Tertiary**: `#A3A3A3`
- **Text Inverse**: `#0F0F0F`

### Border Colors
- **Border Primary**: `#2D2D2D`
- **Border Secondary**: `#404040`
- **Border Focus**: `#60A5FA`

### Component Adjustments

#### Buttons
- **Primary**: Background `#3B82F6`, hover `#2563EB`
- **Secondary**: Border `#60A5FA`, text `#60A5FA`, hover bg `rgba(59, 130, 246, 0.1)`
- **Tertiary**: Hover bg `#262626`, active bg `#2D2D2D`

#### Cards
- **Background**: `#1A1A1A`
- **Border**: `#2D2D2D`
- **Hover**: Background `#1F1F1F`

#### Inputs
- **Background**: `#1A1A1A`
- **Border**: `#404040`
- **Focus Border**: `#60A5FA`
- **Text**: `#FAFAFA`
- **Placeholder**: `#737373`

#### Tables
- **Header**: Background `#1F1F1F`
- **Row**: Background `#1A1A1A`
- **Row Hover**: Background `#262626`
- **Row Selected**: Background `rgba(59, 130, 246, 0.15)`, border `#3B82F6`
- **Border**: `#2D2D2D`

#### Charts
- **Grid Lines**: `#2D2D2D`
- **Axis**: `#404040`
- **Tooltips**: Background `#FAFAFA`, text `#0F0F0F` (inverted for contrast)

### Accent Colors (Dark Mode Adjusted)
- **Accent Primary**: `#60A5FA` (lighter blue for contrast)
- **Accent Secondary**: `#22D3EE` (lighter cyan)
- **Success**: `#34D399` (lighter green)
- **Warning**: `#FBBF24` (lighter orange)
- **Error**: `#F87171` (lighter red)

---

## Responsive Breakpoints

### Screen Sizes
- **Mobile**: `< 768px`
- **Tablet**: `768px - 1023px`
- **Desktop**: `≥ 1024px`
- **Large Desktop**: `≥ 1440px`

### Layout Adjustments

#### Mobile (< 768px)
- **Sidebar**: Hidden by default, hamburger menu
- **Header**: Simplified, essential actions only
- **Tables**: Horizontal scroll or card view
- **Modals**: Full screen or near-full screen
- **Font Sizes**: Slightly reduced (90% scale)
- **Spacing**: Reduced by 25%
- **Button Height**: `40px` minimum for touch targets

#### Tablet (768px - 1023px)
- **Sidebar**: Collapsible, can overlay content
- **Header**: Full features
- **Tables**: Responsive, may hide less critical columns
- **Modals**: Max width `600px`
- **Font Sizes**: Standard
- **Spacing**: Standard

#### Desktop (≥ 1024px)
- **Sidebar**: Always visible, can collapse to icons
- **Header**: Full features, expanded
- **Tables**: Full width, all columns
- **Modals**: Max width `600px` (standard) to `900px` (large)
- **Font Sizes**: Standard
- **Spacing**: Standard

---

## Accessibility

### Contrast Ratios
- **Text Primary on White**: `AAA` (21:1)
- **Text Secondary on White**: `AA` (7:1)
- **Accent Primary on White**: `AA` (4.5:1)
- **White on Accent Primary**: `AAA` (9:1)

### Focus Indicators
- **Outline**: `2px solid #3B82F6`
- **Offset**: `2px`
- **Border Radius**: Match element
- **Never Remove**: Always visible on keyboard focus

### Touch Targets
- **Minimum Size**: `44px × 44px`
- **Spacing**: `8px` minimum between interactive elements
- **Mobile**: All buttons and links meet minimum size

### Screen Reader Support
- **ARIA Labels**: All interactive elements
- **ARIA Live Regions**: For dynamic content updates
- **Semantic HTML**: Proper heading hierarchy, landmarks
- **Alt Text**: All images and icons (decorative marked as such)

### Keyboard Navigation
- **Tab Order**: Logical, follows visual layout
- **Skip Links**: "Skip to main content" for efficiency
- **Arrow Keys**: Support in lists, dropdowns, tables
- **Escape**: Close modals, dropdowns, overlays
- **Enter/Space**: Activate buttons and interactive elements

---

## Best Practices

### Do's
✓ Use the spacing system consistently (4px base unit)
✓ Maintain sharp, clean edges with minimal border radius
✓ Apply monochrome foundation with strategic accent color usage
✓ Ensure all text meets minimum contrast ratios
✓ Use Lucide icons exclusively for consistency
✓ Implement proper focus states for accessibility
✓ Follow the component specifications exactly for visual consistency
✓ Use dark mode palette appropriately when theme is active
✓ Respect animation preferences (reduced motion)
✓ Test all components across breakpoints

### Don'ts
✗ Don't use rounded corners excessively (keep it sharp)
✗ Don't use multiple icon libraries
✗ Don't skip focus indicators
✗ Don't use custom colors outside the defined palette
✗ Don't make touch targets smaller than 44px
✗ Don't use animations longer than 300ms for UI interactions
✗ Don't override accessibility features
✗ Don't use color as the only indicator of state
✗ Don't ignore spacing system (avoid arbitrary values)
✗ Don't mix font weights inconsistently

---

## Implementation Notes

### CSS Variables
Define all colors, spacing, and common values as CSS variables for easy theming and maintenance.

```css
:root {
  /* Primary Colors */
  --color-primary-white: #FFFFFF;
  --color-primary-black: #0F0F0F;
  --color-primary-gray: #1A1A1A;

  /* Accent Colors */
  --color-accent-primary: #3B82F6;
  --color-accent-secondary: #06B6D4;

  /* Spacing */
  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-5: 20px;
  --space-6: 24px;

  /* Typography */
  --font-family-primary: Inter, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
  --font-size-body: 16px;
  --font-weight-regular: 400;
  --font-weight-medium: 500;

  /* Transitions */
  --transition-micro: 150ms ease-out;
  --transition-standard: 200ms ease-out;
}
```

### Tailwind Configuration
Extend Tailwind config to match this design system.

```js
module.exports = {
  theme: {
    extend: {
      colors: {
        'primary-white': '#FFFFFF',
        'primary-black': '#0F0F0F',
        'primary-gray': '#1A1A1A',
        'accent-primary': '#3B82F6',
        // ... all colors
      },
      spacing: {
        '1': '4px',
        '2': '8px',
        '3': '12px',
        // ... all spacing
      },
      fontFamily: {
        sans: ['Inter', 'sans-serif'],
      },
      borderRadius: {
        'sharp': '4px',
        'card': '8px',
      },
    },
  },
}
```

### Component Library Structure
Organize components following this structure:
- `/components/ui/buttons/` - All button variants
- `/components/ui/cards/` - Card components
- `/components/ui/forms/` - Form inputs, selects, etc.
- `/components/ui/navigation/` - Sidebar, header, footer
- `/components/ui/modals/` - Modal and dialog components
- `/components/ui/tables/` - Table components
- `/components/ui/charts/` - Chart components
- `/components/ui/icons/` - Icon wrapper components

---

## Version History

**Version 1.0** - Initial release (2025-11-20)
- Complete design system specification
- All core components defined
- Accessibility guidelines included
- Dark mode support
- Responsive design specifications

---

## Maintenance & Updates

This design system is a living document. All updates should:
1. Maintain consistency with existing patterns
2. Consider accessibility impact
3. Update all affected components
4. Document changes in version history
5. Communicate changes to the development team

For questions or suggestions, refer to the product design team.

---

**End of Style Guide**
