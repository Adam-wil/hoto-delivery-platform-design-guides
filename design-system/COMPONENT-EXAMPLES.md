# Component Implementation Examples

This document provides practical code examples for implementing the HOTO Delivery Platform UI components using React and Tailwind CSS.

---

## Table of Contents
1. [Headers](#headers)
2. [Sidebar Navigation](#sidebar-navigation)
3. [Footers](#footers)
4. [Tables](#tables)
5. [Buttons](#buttons)
6. [Toggle Switches](#toggle-switches)
7. [Modals](#modals)
8. [Hamburger Menu](#hamburger-menu)
9. [Charts](#charts)
10. [Forms](#forms)
11. [Cards](#cards)

---

## Headers

### Main Application Header

```jsx
import { Menu, Bell, Settings, User } from 'lucide-react';

const AppHeader = () => {
  return (
    <header className="h-16 bg-[#1A1A1A] border-b border-[#2D2D2D] px-6 flex items-center justify-between">
      {/* Left: Logo/Brand */}
      <div className="flex items-center gap-3">
        <img src="/logo.svg" alt="HOTO" className="h-8" />
        <h1 className="text-white text-lg font-semibold">HOTO Delivery</h1>
      </div>

      {/* Right: Actions */}
      <div className="flex items-center gap-2">
        <button className="w-10 h-10 flex items-center justify-center rounded-md hover:bg-white/10 transition-colors">
          <Bell className="w-6 h-6 text-white" />
        </button>
        <button className="w-10 h-10 flex items-center justify-center rounded-md hover:bg-white/10 transition-colors">
          <Settings className="w-6 h-6 text-white" />
        </button>
        <button className="w-10 h-10 flex items-center justify-center rounded-md hover:bg-white/10 transition-colors">
          <User className="w-6 h-6 text-white" />
        </button>
      </div>
    </header>
  );
};
```

### Section Header

```jsx
import { Plus } from 'lucide-react';

const SectionHeader = ({ title, onAddClick }) => {
  return (
    <div className="h-14 bg-white border-b border-[#E5E5E5] px-6 flex items-center justify-between">
      <h2 className="text-2xl font-bold text-[#0F0F0F]">{title}</h2>
      <button
        onClick={onAddClick}
        className="h-11 px-6 bg-[#3B82F6] text-white rounded-md font-medium hover:bg-[#2563EB] transition-all shadow-sm hover:shadow"
      >
        <Plus className="w-5 h-5 inline-block mr-2" />
        Add New
      </button>
    </div>
  );
};
```

---

## Sidebar Navigation

### Primary Sidebar

```jsx
import {
  Home,
  Package,
  Truck,
  BarChart,
  Settings,
  User,
  ChevronLeft,
  ChevronRight
} from 'lucide-react';
import { useState } from 'react';

const Sidebar = () => {
  const [isCollapsed, setIsCollapsed] = useState(false);
  const [activeItem, setActiveItem] = useState('dashboard');

  const navItems = [
    { id: 'dashboard', label: 'Dashboard', icon: Home },
    { id: 'orders', label: 'Orders', icon: Package },
    { id: 'deliveries', label: 'Deliveries', icon: Truck },
    { id: 'analytics', label: 'Analytics', icon: BarChart },
    { id: 'settings', label: 'Settings', icon: Settings },
  ];

  return (
    <aside
      className={`bg-[#1A1A1A] border-r border-[#2D2D2D] py-6 transition-all duration-250 ease-out ${
        isCollapsed ? 'w-16' : 'w-70'
      }`}
    >
      {/* Sidebar Header */}
      <div className={`px-5 pb-6 border-b border-[#2D2D2D] mb-4 ${isCollapsed ? 'hidden' : 'block'}`}>
        <img src="/logo-light.svg" alt="HOTO" className="h-10" />
      </div>

      {/* Navigation Items */}
      <nav className="px-3">
        {navItems.map((item) => {
          const Icon = item.icon;
          const isActive = activeItem === item.id;

          return (
            <button
              key={item.id}
              onClick={() => setActiveItem(item.id)}
              className={`w-full h-12 flex items-center gap-3 px-4 mb-1 rounded-md transition-all ${
                isActive
                  ? 'bg-[#3B82F6]/15 text-[#60A5FA]'
                  : 'text-[#D4D4D4] hover:bg-white/8'
              }`}
            >
              <Icon className="w-6 h-6 flex-shrink-0" />
              {!isCollapsed && <span className="text-sm font-medium">{item.label}</span>}
            </button>
          );
        })}
      </nav>

      {/* Toggle Button */}
      <button
        onClick={() => setIsCollapsed(!isCollapsed)}
        className="absolute bottom-6 right-4 w-8 h-8 bg-[#2D2D2D] rounded-md flex items-center justify-center hover:bg-[#404040]"
      >
        {isCollapsed ? (
          <ChevronRight className="w-4 h-4 text-white" />
        ) : (
          <ChevronLeft className="w-4 h-4 text-white" />
        )}
      </button>

      {/* User Profile (Footer) */}
      {!isCollapsed && (
        <div className="absolute bottom-0 left-0 right-0 border-t border-[#2D2D2D] p-5">
          <div className="flex items-center gap-3">
            <div className="w-9 h-9 rounded-full bg-[#3B82F6] flex items-center justify-center">
              <User className="w-5 h-5 text-white" />
            </div>
            <div>
              <p className="text-sm font-medium text-white">John Doe</p>
              <p className="text-xs text-[#A3A3A3]">Administrator</p>
            </div>
          </div>
        </div>
      )}
    </aside>
  );
};
```

---

## Footers

### Application Footer

```jsx
const AppFooter = () => {
  return (
    <footer className="h-14 bg-[#1A1A1A] border-t border-[#2D2D2D] px-6 flex items-center justify-between">
      <p className="text-sm text-[#D4D4D4]">
        © 2025 HOTO Delivery Platform. All rights reserved.
      </p>
      <div className="flex items-center gap-6">
        <a href="/privacy" className="text-sm text-[#A3A3A3] hover:text-white transition-colors">
          Privacy Policy
        </a>
        <a href="/terms" className="text-sm text-[#A3A3A3] hover:text-white transition-colors">
          Terms of Service
        </a>
        <span className="text-sm text-[#737373]">v1.0.0</span>
      </div>
    </footer>
  );
};
```

---

## Tables

### Data Table

```jsx
import { Edit, Trash, Eye, MoreVertical } from 'lucide-react';

const DataTable = ({ data }) => {
  const [selectedRow, setSelectedRow] = useState(null);

  return (
    <div className="bg-white border border-[#E5E5E5] rounded-lg shadow-sm overflow-hidden">
      <table className="w-full">
        <thead className="bg-[#F9FAFB] border-b border-[#E5E5E5]">
          <tr>
            <th className="h-12 px-4 text-left text-sm font-semibold text-[#0F0F0F] uppercase tracking-wide">
              Order ID
            </th>
            <th className="h-12 px-4 text-left text-sm font-semibold text-[#0F0F0F] uppercase tracking-wide">
              Customer
            </th>
            <th className="h-12 px-4 text-left text-sm font-semibold text-[#0F0F0F] uppercase tracking-wide">
              Status
            </th>
            <th className="h-12 px-4 text-right text-sm font-semibold text-[#0F0F0F] uppercase tracking-wide">
              Amount
            </th>
            <th className="h-12 px-4 text-center text-sm font-semibold text-[#0F0F0F] uppercase tracking-wide">
              Actions
            </th>
          </tr>
        </thead>
        <tbody>
          {data.map((row) => (
            <tr
              key={row.id}
              onClick={() => setSelectedRow(row.id)}
              className={`h-14 border-b border-[#F5F5F5] hover:bg-[#FAFAFA] transition-colors cursor-pointer ${
                selectedRow === row.id ? 'bg-[#EFF6FF] border-l-4 border-l-[#3B82F6]' : ''
              }`}
            >
              <td className="px-4 text-sm font-mono text-[#0F0F0F]">{row.id}</td>
              <td className="px-4 text-sm text-[#0F0F0F]">{row.customer}</td>
              <td className="px-4">
                <span className={`inline-flex items-center px-2.5 py-1 rounded text-xs font-medium ${
                  row.status === 'Completed'
                    ? 'bg-[#10B981]/10 text-[#10B981]'
                    : row.status === 'Pending'
                    ? 'bg-[#F59E0B]/10 text-[#F59E0B]'
                    : 'bg-[#3B82F6]/10 text-[#3B82F6]'
                }`}>
                  {row.status}
                </span>
              </td>
              <td className="px-4 text-sm text-right font-mono text-[#0F0F0F]">
                ${row.amount.toFixed(2)}
              </td>
              <td className="px-4">
                <div className="flex items-center justify-center gap-2">
                  <button className="w-8 h-8 flex items-center justify-center rounded hover:bg-[#F5F5F5]">
                    <Eye className="w-5 h-5 text-[#737373] hover:text-[#0F0F0F]" />
                  </button>
                  <button className="w-8 h-8 flex items-center justify-center rounded hover:bg-[#F5F5F5]">
                    <Edit className="w-5 h-5 text-[#737373] hover:text-[#0F0F0F]" />
                  </button>
                  <button className="w-8 h-8 flex items-center justify-center rounded hover:bg-[#F5F5F5]">
                    <Trash className="w-5 h-5 text-[#737373] hover:text-[#EF4444]" />
                  </button>
                </div>
              </td>
            </tr>
          ))}
        </tbody>
      </table>

      {/* Empty State */}
      {data.length === 0 && (
        <div className="py-12 text-center">
          <Package className="w-12 h-12 text-[#D4D4D4] mx-auto mb-3" />
          <p className="text-base text-[#525252]">No orders found</p>
          <button className="mt-4 h-11 px-6 border-2 border-[#3B82F6] text-[#3B82F6] rounded-md font-medium hover:bg-[#EFF6FF]">
            Create First Order
          </button>
        </div>
      )}
    </div>
  );
};
```

---

## Buttons

### Button Variants

```jsx
import { Save, Trash, Download, Plus } from 'lucide-react';

const ButtonExamples = () => {
  return (
    <div className="flex flex-wrap gap-4">
      {/* Primary Button */}
      <button className="h-11 px-6 bg-[#3B82F6] text-white rounded-md font-medium hover:bg-[#2563EB] active:bg-[#1D4ED8] focus:outline-none focus:ring-2 focus:ring-[#93C5FD] focus:ring-offset-2 shadow-sm transition-all">
        <Save className="w-5 h-5 inline-block mr-2" />
        Save Changes
      </button>

      {/* Secondary Button */}
      <button className="h-11 px-6 border-2 border-[#3B82F6] text-[#3B82F6] bg-transparent rounded-md font-medium hover:bg-[#EFF6FF] hover:border-[#2563EB] active:bg-[#DBEAFE] focus:outline-none focus:ring-2 focus:ring-[#93C5FD] focus:ring-offset-2 transition-all">
        <Download className="w-5 h-5 inline-block mr-2" />
        Export
      </button>

      {/* Tertiary/Ghost Button */}
      <button className="h-11 px-6 text-[#0F0F0F] bg-transparent rounded-md font-medium hover:bg-[#F5F5F5] active:bg-[#E5E5E5] focus:outline-none focus:ring-2 focus:ring-[#3B82F6] focus:ring-offset-2 transition-all">
        Cancel
      </button>

      {/* Destructive Button */}
      <button className="h-11 px-6 bg-[#EF4444] text-white rounded-md font-medium hover:bg-[#DC2626] active:bg-[#B91C1C] focus:outline-none focus:ring-2 focus:ring-[#FCA5A5] focus:ring-offset-2 shadow-sm transition-all">
        <Trash className="w-5 h-5 inline-block mr-2" />
        Delete
      </button>

      {/* Icon Button */}
      <button className="w-10 h-10 flex items-center justify-center bg-transparent rounded-md hover:bg-[#F5F5F5] active:bg-[#E5E5E5] focus:outline-none focus:ring-2 focus:ring-[#3B82F6] focus:ring-offset-2 transition-all">
        <Plus className="w-5 h-5 text-[#525252]" />
      </button>

      {/* Disabled Button */}
      <button
        disabled
        className="h-11 px-6 bg-[#E5E5E5] text-[#A3A3A3] rounded-md font-medium cursor-not-allowed"
      >
        Disabled
      </button>
    </div>
  );
};
```

---

## Toggle Switches

### Toggle Switch Component

```jsx
import { useState } from 'react';

const ToggleSwitch = ({ label, defaultChecked = false, onChange }) => {
  const [isOn, setIsOn] = useState(defaultChecked);

  const handleToggle = () => {
    const newState = !isOn;
    setIsOn(newState);
    onChange?.(newState);
  };

  return (
    <div className="flex items-center gap-3">
      <button
        onClick={handleToggle}
        className={`relative w-12 h-6 rounded-full transition-all duration-200 focus:outline-none focus:ring-2 focus:ring-[#93C5FD] focus:ring-offset-2 ${
          isOn ? 'bg-[#3B82F6]' : 'bg-[#D4D4D4]'
        }`}
        role="switch"
        aria-checked={isOn}
      >
        <span
          className={`absolute top-0.5 left-0.5 w-5 h-5 bg-white rounded-full shadow-md transition-transform duration-200 ${
            isOn ? 'translate-x-6' : 'translate-x-0'
          }`}
        />
      </button>
      {label && (
        <label className="text-base text-[#0F0F0F] cursor-pointer" onClick={handleToggle}>
          {label}
        </label>
      )}
    </div>
  );
};

// Usage Example
const ToggleExamples = () => {
  return (
    <div className="space-y-4">
      <ToggleSwitch label="Enable notifications" defaultChecked={true} />
      <ToggleSwitch label="Auto-save changes" defaultChecked={false} />
      <ToggleSwitch label="Dark mode" defaultChecked={false} />
    </div>
  );
};
```

---

## Modals

### Modal Component

```jsx
import { X } from 'lucide-react';
import { useEffect } from 'react';

const Modal = ({ isOpen, onClose, title, children, footer }) => {
  useEffect(() => {
    if (isOpen) {
      document.body.style.overflow = 'hidden';
    } else {
      document.body.style.overflow = 'unset';
    }
    return () => {
      document.body.style.overflow = 'unset';
    };
  }, [isOpen]);

  if (!isOpen) return null;

  return (
    <>
      {/* Overlay */}
      <div
        className="fixed inset-0 bg-[rgba(15,15,15,0.6)] backdrop-blur-sm z-[1000] animate-fadeIn"
        onClick={onClose}
      />

      {/* Modal Container */}
      <div className="fixed inset-0 z-[1001] flex items-center justify-center p-4">
        <div
          className="bg-white rounded-lg shadow-2xl max-w-xl w-full max-h-[90vh] flex flex-col animate-scaleIn"
          onClick={(e) => e.stopPropagation()}
        >
          {/* Header */}
          <div className="px-6 pt-6 pb-4 border-b border-[#E5E5E5] flex items-center justify-between">
            <h2 className="text-2xl font-bold text-[#0F0F0F]">{title}</h2>
            <button
              onClick={onClose}
              className="w-10 h-10 flex items-center justify-center rounded-md hover:bg-[#F5F5F5] transition-colors"
            >
              <X className="w-6 h-6 text-[#525252]" />
            </button>
          </div>

          {/* Body */}
          <div className="px-6 py-6 overflow-y-auto">
            {children}
          </div>

          {/* Footer */}
          {footer && (
            <div className="px-6 pt-4 pb-6 border-t border-[#E5E5E5] flex items-center justify-end gap-2">
              {footer}
            </div>
          )}
        </div>
      </div>
    </>
  );
};

// Usage Example
const ModalExample = () => {
  const [isOpen, setIsOpen] = useState(false);

  return (
    <>
      <button
        onClick={() => setIsOpen(true)}
        className="h-11 px-6 bg-[#3B82F6] text-white rounded-md font-medium"
      >
        Open Modal
      </button>

      <Modal
        isOpen={isOpen}
        onClose={() => setIsOpen(false)}
        title="Confirm Action"
        footer={
          <>
            <button
              onClick={() => setIsOpen(false)}
              className="h-11 px-6 text-[#0F0F0F] bg-transparent rounded-md font-medium hover:bg-[#F5F5F5]"
            >
              Cancel
            </button>
            <button
              onClick={() => {
                // Handle action
                setIsOpen(false);
              }}
              className="h-11 px-6 bg-[#3B82F6] text-white rounded-md font-medium hover:bg-[#2563EB]"
            >
              Confirm
            </button>
          </>
        }
      >
        <p className="text-base text-[#0F0F0F]">
          Are you sure you want to proceed with this action? This cannot be undone.
        </p>
      </Modal>
    </>
  );
};
```

---

## Hamburger Menu

### Hamburger Menu Component

```jsx
import { useState } from 'react';
import { Home, Package, Truck, BarChart, Settings, X } from 'lucide-react';

const HamburgerMenu = () => {
  const [isOpen, setIsOpen] = useState(false);

  const menuItems = [
    { icon: Home, label: 'Dashboard', href: '/dashboard' },
    { icon: Package, label: 'Orders', href: '/orders' },
    { icon: Truck, label: 'Deliveries', href: '/deliveries' },
    { icon: BarChart, label: 'Analytics', href: '/analytics' },
    { icon: Settings, label: 'Settings', href: '/settings' },
  ];

  return (
    <>
      {/* Hamburger Button */}
      <button
        onClick={() => setIsOpen(!isOpen)}
        className="w-10 h-10 flex flex-col items-center justify-center gap-1.5 rounded-md hover:bg-[#F5F5F5] transition-all"
        aria-label="Menu"
      >
        <span
          className={`w-6 h-0.5 bg-[#0F0F0F] rounded-full transition-all duration-250 ${
            isOpen ? 'rotate-45 translate-y-2' : ''
          }`}
        />
        <span
          className={`w-6 h-0.5 bg-[#0F0F0F] rounded-full transition-all duration-250 ${
            isOpen ? 'opacity-0' : ''
          }`}
        />
        <span
          className={`w-6 h-0.5 bg-[#0F0F0F] rounded-full transition-all duration-250 ${
            isOpen ? '-rotate-45 -translate-y-2' : ''
          }`}
        />
      </button>

      {/* Overlay */}
      {isOpen && (
        <div
          className="fixed inset-0 bg-[rgba(15,15,15,0.6)] z-[998] animate-fadeIn"
          onClick={() => setIsOpen(false)}
        />
      )}

      {/* Menu Panel */}
      <div
        className={`fixed top-0 right-0 h-screen w-70 bg-[#1A1A1A] shadow-2xl z-[999] transition-transform duration-300 ease-out ${
          isOpen ? 'translate-x-0' : 'translate-x-full'
        }`}
      >
        {/* Menu Header */}
        <div className="h-16 px-6 flex items-center justify-between border-b border-[#2D2D2D]">
          <h2 className="text-lg font-semibold text-white">Menu</h2>
          <button
            onClick={() => setIsOpen(false)}
            className="w-10 h-10 flex items-center justify-center rounded-md hover:bg-white/10"
          >
            <X className="w-6 h-6 text-white" />
          </button>
        </div>

        {/* Menu Items */}
        <nav className="p-4">
          {menuItems.map((item) => {
            const Icon = item.icon;
            return (
              <a
                key={item.href}
                href={item.href}
                className="flex items-center gap-3 h-12 px-4 mb-1 rounded-md text-[#D4D4D4] hover:bg-white/8 hover:text-white transition-all"
                onClick={() => setIsOpen(false)}
              >
                <Icon className="w-6 h-6" />
                <span className="text-sm font-medium">{item.label}</span>
              </a>
            );
          })}
        </nav>
      </div>
    </>
  );
};
```

---

## Charts

### Bar Chart Example (using Recharts)

```jsx
import { BarChart, Bar, XAxis, YAxis, CartesianGrid, Tooltip, ResponsiveContainer } from 'recharts';

const data = [
  { month: 'Jan', revenue: 4200, orders: 145 },
  { month: 'Feb', revenue: 3800, orders: 132 },
  { month: 'Mar', revenue: 5100, orders: 178 },
  { month: 'Apr', revenue: 4700, orders: 162 },
  { month: 'May', revenue: 6200, orders: 215 },
  { month: 'Jun', revenue: 5800, orders: 198 },
];

const CustomTooltip = ({ active, payload }) => {
  if (active && payload && payload.length) {
    return (
      <div className="bg-[#0F0F0F] text-white px-3 py-2 rounded-md shadow-lg">
        <p className="text-sm font-medium">{payload[0].payload.month}</p>
        <p className="text-xs">Revenue: ${payload[0].value}</p>
        <p className="text-xs">Orders: {payload[1].value}</p>
      </div>
    );
  }
  return null;
};

const RevenueChart = () => {
  return (
    <div className="bg-white border border-[#E5E5E5] rounded-lg p-6 shadow-sm">
      <h3 className="text-xl font-semibold text-[#0F0F0F] mb-5">Monthly Revenue</h3>

      <ResponsiveContainer width="100%" height={300}>
        <BarChart data={data}>
          <CartesianGrid strokeDasharray="4 4" stroke="#F5F5F5" />
          <XAxis
            dataKey="month"
            stroke="#737373"
            style={{ fontSize: '12px', fontWeight: 500 }}
          />
          <YAxis
            stroke="#737373"
            style={{ fontSize: '12px', fontWeight: 500 }}
          />
          <Tooltip content={<CustomTooltip />} />
          <Bar dataKey="revenue" fill="#3B82F6" radius={[4, 4, 0, 0]} />
          <Bar dataKey="orders" fill="#10B981" radius={[4, 4, 0, 0]} />
        </BarChart>
      </ResponsiveContainer>

      {/* Legend */}
      <div className="flex items-center justify-center gap-6 mt-4">
        <div className="flex items-center gap-2">
          <div className="w-3 h-3 bg-[#3B82F6] rounded" />
          <span className="text-sm font-medium text-[#525252]">Revenue</span>
        </div>
        <div className="flex items-center gap-2">
          <div className="w-3 h-3 bg-[#10B981] rounded" />
          <span className="text-sm font-medium text-[#525252]">Orders</span>
        </div>
      </div>
    </div>
  );
};
```

### Pie Chart Example (using Recharts)

```jsx
import { PieChart, Pie, Cell, ResponsiveContainer, Legend, Tooltip } from 'recharts';

const data = [
  { name: 'Completed', value: 450 },
  { name: 'In Transit', value: 230 },
  { name: 'Pending', value: 180 },
  { name: 'Cancelled', value: 45 },
];

const COLORS = ['#3B82F6', '#06B6D4', '#10B981', '#8B5CF6'];

const DeliveryStatusPieChart = () => {
  return (
    <div className="bg-white border border-[#E5E5E5] rounded-lg p-6 shadow-sm">
      <h3 className="text-xl font-semibold text-[#0F0F0F] mb-5">Delivery Status</h3>

      <ResponsiveContainer width="100%" height={300}>
        <PieChart>
          <Pie
            data={data}
            cx="50%"
            cy="50%"
            labelLine={false}
            outerRadius={100}
            fill="#8884d8"
            dataKey="value"
            stroke="#FFFFFF"
            strokeWidth={2}
          >
            {data.map((entry, index) => (
              <Cell key={`cell-${index}`} fill={COLORS[index % COLORS.length]} />
            ))}
          </Pie>
          <Tooltip
            contentStyle={{
              backgroundColor: '#0F0F0F',
              color: '#FFFFFF',
              border: 'none',
              borderRadius: '6px',
              padding: '8px 12px',
              fontSize: '13px',
              fontWeight: 500,
            }}
          />
        </PieChart>
      </ResponsiveContainer>

      {/* Custom Legend */}
      <div className="grid grid-cols-2 gap-4 mt-4">
        {data.map((entry, index) => (
          <div key={entry.name} className="flex items-center gap-2">
            <div
              className="w-3 h-3 rounded-full"
              style={{ backgroundColor: COLORS[index] }}
            />
            <span className="text-sm font-medium text-[#525252]">
              {entry.name}: {entry.value}
            </span>
          </div>
        ))}
      </div>
    </div>
  );
};
```

---

## Forms

### Form Input Components

```jsx
const FormExample = () => {
  return (
    <form className="bg-white border border-[#E5E5E5] rounded-lg p-6 space-y-5">
      {/* Text Input */}
      <div>
        <label className="block text-sm font-medium text-[#525252] mb-2">
          Full Name
        </label>
        <input
          type="text"
          placeholder="Enter your full name"
          className="w-full h-11 px-4 bg-white border border-[#D4D4D4] rounded-md text-base text-[#0F0F0F] placeholder:text-[#737373] focus:outline-none focus:border-2 focus:border-[#3B82F6] transition-all"
        />
      </div>

      {/* Email Input */}
      <div>
        <label className="block text-sm font-medium text-[#525252] mb-2">
          Email Address
        </label>
        <input
          type="email"
          placeholder="you@example.com"
          className="w-full h-11 px-4 bg-white border border-[#D4D4D4] rounded-md text-base text-[#0F0F0F] placeholder:text-[#737373] focus:outline-none focus:border-2 focus:border-[#3B82F6] transition-all"
        />
      </div>

      {/* Select Dropdown */}
      <div>
        <label className="block text-sm font-medium text-[#525252] mb-2">
          Role
        </label>
        <select className="w-full h-11 px-4 bg-white border border-[#D4D4D4] rounded-md text-base text-[#0F0F0F] focus:outline-none focus:border-2 focus:border-[#3B82F6] transition-all">
          <option value="">Select a role</option>
          <option value="admin">Administrator</option>
          <option value="manager">Manager</option>
          <option value="driver">Driver</option>
        </select>
      </div>

      {/* Textarea */}
      <div>
        <label className="block text-sm font-medium text-[#525252] mb-2">
          Message
        </label>
        <textarea
          rows={4}
          placeholder="Enter your message..."
          className="w-full px-4 py-3 bg-white border border-[#D4D4D4] rounded-md text-base text-[#0F0F0F] placeholder:text-[#737373] resize-y focus:outline-none focus:border-2 focus:border-[#3B82F6] transition-all"
        />
      </div>

      {/* Checkbox */}
      <div className="flex items-center gap-3">
        <input
          type="checkbox"
          id="terms"
          className="w-5 h-5 border-2 border-[#D4D4D4] rounded text-[#3B82F6] focus:ring-2 focus:ring-[#93C5FD] focus:ring-offset-2"
        />
        <label htmlFor="terms" className="text-base text-[#0F0F0F]">
          I agree to the terms and conditions
        </label>
      </div>

      {/* Radio Buttons */}
      <div>
        <label className="block text-sm font-medium text-[#525252] mb-3">
          Notification Preference
        </label>
        <div className="space-y-2">
          <div className="flex items-center gap-3">
            <input
              type="radio"
              id="email-notif"
              name="notification"
              className="w-5 h-5 border-2 border-[#D4D4D4] text-[#3B82F6] focus:ring-2 focus:ring-[#93C5FD] focus:ring-offset-2"
            />
            <label htmlFor="email-notif" className="text-base text-[#0F0F0F]">
              Email notifications
            </label>
          </div>
          <div className="flex items-center gap-3">
            <input
              type="radio"
              id="sms-notif"
              name="notification"
              className="w-5 h-5 border-2 border-[#D4D4D4] text-[#3B82F6] focus:ring-2 focus:ring-[#93C5FD] focus:ring-offset-2"
            />
            <label htmlFor="sms-notif" className="text-base text-[#0F0F0F]">
              SMS notifications
            </label>
          </div>
        </div>
      </div>

      {/* Submit Buttons */}
      <div className="flex items-center justify-end gap-2 pt-4">
        <button
          type="button"
          className="h-11 px-6 text-[#0F0F0F] bg-transparent rounded-md font-medium hover:bg-[#F5F5F5] transition-all"
        >
          Cancel
        </button>
        <button
          type="submit"
          className="h-11 px-6 bg-[#3B82F6] text-white rounded-md font-medium hover:bg-[#2563EB] shadow-sm transition-all"
        >
          Submit
        </button>
      </div>
    </form>
  );
};
```

---

## Cards

### Card Variants

```jsx
import { Package, TrendingUp, Users, DollarSign } from 'lucide-react';

const CardExamples = () => {
  return (
    <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-5">
      {/* Stat Card 1 */}
      <div className="bg-white border border-[#E5E5E5] rounded-lg p-5 shadow-sm hover:shadow-md transition-shadow">
        <div className="flex items-center justify-between mb-3">
          <div className="w-12 h-12 bg-[#3B82F6]/10 rounded-md flex items-center justify-center">
            <Package className="w-6 h-6 text-[#3B82F6]" />
          </div>
          <span className="text-xs font-medium text-[#10B981] flex items-center gap-1">
            <TrendingUp className="w-3 h-3" />
            12.5%
          </span>
        </div>
        <h3 className="text-3xl font-bold text-[#0F0F0F] mb-1">1,284</h3>
        <p className="text-sm text-[#525252]">Total Orders</p>
      </div>

      {/* Stat Card 2 */}
      <div className="bg-white border border-[#E5E5E5] rounded-lg p-5 shadow-sm hover:shadow-md transition-shadow">
        <div className="flex items-center justify-between mb-3">
          <div className="w-12 h-12 bg-[#10B981]/10 rounded-md flex items-center justify-center">
            <TrendingUp className="w-6 h-6 text-[#10B981]" />
          </div>
          <span className="text-xs font-medium text-[#10B981] flex items-center gap-1">
            <TrendingUp className="w-3 h-3" />
            8.2%
          </span>
        </div>
        <h3 className="text-3xl font-bold text-[#0F0F0F] mb-1">$45,231</h3>
        <p className="text-sm text-[#525252]">Revenue</p>
      </div>

      {/* Stat Card 3 */}
      <div className="bg-white border border-[#E5E5E5] rounded-lg p-5 shadow-sm hover:shadow-md transition-shadow">
        <div className="flex items-center justify-between mb-3">
          <div className="w-12 h-12 bg-[#8B5CF6]/10 rounded-md flex items-center justify-center">
            <Users className="w-6 h-6 text-[#8B5CF6]" />
          </div>
          <span className="text-xs font-medium text-[#10B981] flex items-center gap-1">
            <TrendingUp className="w-3 h-3" />
            5.7%
          </span>
        </div>
        <h3 className="text-3xl font-bold text-[#0F0F0F] mb-1">892</h3>
        <p className="text-sm text-[#525252]">Active Users</p>
      </div>

      {/* Stat Card 4 */}
      <div className="bg-white border border-[#E5E5E5] rounded-lg p-5 shadow-sm hover:shadow-md transition-shadow">
        <div className="flex items-center justify-between mb-3">
          <div className="w-12 h-12 bg-[#F59E0B]/10 rounded-md flex items-center justify-center">
            <DollarSign className="w-6 h-6 text-[#F59E0B]" />
          </div>
          <span className="text-xs font-medium text-[#EF4444] flex items-center gap-1">
            <TrendingUp className="w-3 h-3 rotate-180" />
            3.1%
          </span>
        </div>
        <h3 className="text-3xl font-bold text-[#0F0F0F] mb-1">$12.5K</h3>
        <p className="text-sm text-[#525252]">Avg. Order Value</p>
      </div>
    </div>
  );
};
```

---

## Tailwind CSS Configuration

Add these custom utilities to your `tailwind.config.js`:

```js
module.exports = {
  theme: {
    extend: {
      colors: {
        // Custom color palette
        'primary-black': '#0F0F0F',
        'primary-gray': '#1A1A1A',
        'accent-primary': '#3B82F6',
        // Add all colors from style guide
      },
      spacing: {
        '70': '280px', // Sidebar width
      },
      keyframes: {
        fadeIn: {
          '0%': { opacity: '0' },
          '100%': { opacity: '1' },
        },
        scaleIn: {
          '0%': { opacity: '0', transform: 'scale(0.95)' },
          '100%': { opacity: '1', transform: 'scale(1)' },
        },
      },
      animation: {
        fadeIn: 'fadeIn 200ms ease-out',
        scaleIn: 'scaleIn 250ms ease-out',
      },
    },
  },
  plugins: [],
};
```

---

## CSS Animations

Add these animations to your global CSS:

```css
@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
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

@keyframes slideInRight {
  from {
    transform: translateX(100%);
  }
  to {
    transform: translateX(0);
  }
}

/* Smooth transitions */
* {
  transition-timing-function: cubic-bezier(0, 0, 0.2, 1);
}

/* Respect reduced motion preferences */
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

---

## Usage Notes

1. **Lucide Icons**: Install with `npm install lucide-react`
2. **Recharts**: Install with `npm install recharts` for charts
3. **Tailwind CSS**: Ensure Tailwind is properly configured
4. **Accessibility**: All components include proper ARIA labels and keyboard navigation
5. **Responsive**: Components adapt to mobile, tablet, and desktop breakpoints
6. **Dark Mode**: Use the dark mode color palette from the style guide

---

**For more details, refer to the [UI Style Guide](./UI-STYLE-GUIDE.md)**
