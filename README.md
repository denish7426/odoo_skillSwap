# React + Tailwind CSS Setup

This is a modern React application built with Vite and styled with Tailwind CSS.

## Features

- ⚡️ **Vite** - Fast build tool and development server
- ⚛️ **React 19** - Latest React with modern features
- 🎨 **Tailwind CSS** - Utility-first CSS framework
- 🔧 **PostCSS** - CSS processing with autoprefixer
- 📦 **ESLint** - Code linting and formatting

## Getting Started

### Prerequisites

- Node.js (version 16 or higher)
- npm or yarn

### Installation

1. Install dependencies:
```bash
npm install
```

2. Start the development server:
```bash
npm run dev
```

3. Open your browser and navigate to `http://localhost:5173`

## Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build
- `npm run lint` - Run ESLint

## Project Structure

```
src/
├── App.jsx          # Main application component
├── main.jsx         # Application entry point
├── index.css        # Global styles with Tailwind directives
└── assets/          # Static assets
```

## Tailwind CSS

This project uses Tailwind CSS for styling. The configuration is in `tailwind.config.js` and includes:

- Custom animations (like `animate-spin-slow`)
- Responsive design utilities
- Custom color schemes and spacing

## Customization

You can customize the Tailwind configuration by editing `tailwind.config.js`. The current setup includes:

- Content paths for all React components
- Custom animations
- Extensible theme configuration

## Learn More

- [React Documentation](https://react.dev/)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [Vite Documentation](https://vitejs.dev/)
