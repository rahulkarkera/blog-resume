# Personal Portfolio & Blog

This is a personalized portfolio website showcasing my professional experience, skills, and technical blog posts. Built with modern web technologies for optimal performance and user experience.

## ✨ Features

- **Astro v4** - Fast, content-focused static site generation with hybrid rendering
- **Resume Homepage** - Professional portfolio with experience, education, and skills sections
- **Blog System** - MDX/Markdown blog with pagination, tags, and reading time
- **Multi-Theme Support** - Light, Dark, and System modes with smooth transitions
- **Fully Responsive** - Mobile-first design with Tailwind CSS
- **SEO Optimized** - Semantic HTML, meta tags, and automatic sitemap
- **RSS Feed** - Automatic feed generation for blog posts
- **Code Highlighting** - Expressive Code with dracula/github-light themes
- **Performance** - Optimized images with Astro Assets Integration

## 🛠️ Tech Stack

- **Framework**: Astro v4.16.19 (Hybrid mode)
- **Styling**: Tailwind CSS with custom design system
- **Deployment**: Cloudflare Pages
- **Content**: MDX/Markdown with Zod validation
- **Icons**: astro-icon with custom SVG icons
- **Package Manager**: pnpm

## 📂 Project Structure

```text
├── public/
│   ├── fonts/           # Custom fonts
│   ├── images/          # Static images
│   └── favicon/         # Favicon assets
├── src/
│   ├── assets/          # Optimized images (profile photo, etc.)
│   ├── components/      # Reusable UI components
│   │   ├── blog/        # Blog-specific components
│   │   └── layout/      # Header, Footer
│   ├── content/
│   │   ├── post/        # Blog posts (MDX/Markdown)
│   │   ├── _examples/   # Template posts for reference
│   │   └── config.ts    # Content schema (Zod)
│   ├── icons/           # Custom SVG icons
│   ├── layouts/         # Page layouts
│   ├── pages/           # Routes
│   │   ├── blog/        # Blog routes with pagination
│   │   ├── tags/        # Tag-based filtering
│   │   └── tools/       # Development tools showcase
│   ├── styles/          # Global CSS and theme variables
│   ├── utils/           # Helper functions
│   └── site.config.ts   # Site-wide configuration
├── astro.config.mjs     # Astro configuration
├── tailwind.config.js   # Tailwind configuration
└── tsconfig.json        # TypeScript configuration
```

## 🚀 Getting Started

### Prerequisites

- Node.js 18+
- pnpm (recommended) or npm

### Installation

```bash
# Install pnpm globally (if not already installed)
npm install -g pnpm

# Install dependencies
pnpm install

# Start development server
pnpm dev

# Build for production
pnpm build

# Preview production build
pnpm preview
```

The dev server will start at `http://localhost:4321/`

## ✏️ Content Management

### Personal Information

Edit `src/site.config.ts` to update:
- Site title and description
- Author name
- Social media links
- Date formatting preferences

### Homepage Content

Edit `src/pages/index.astro` to update:
- Profile photo (stored in `src/assets/`)
- About section
- Work experience
- Education
- Skills (organized by categories)

### Blog Posts

1. **Create a new post**: Copy a template from `src/content/_examples/` to `src/content/post/`
2. **Update frontmatter**:
   ```yaml
   ---
   title: "Your Post Title"
   description: "Brief description (50-160 characters)"
   publishDate: "16 Nov 2025"
   tags: ["tag1", "tag2"]
   draft: false  # Set to true to hide from production
   ---
   ```
3. **Add content**: Write your post in Markdown/MDX
4. **Images**: Place in the same folder as your post and reference relatively

### Tools Page

Edit `src/pages/tools/index.astro` to add/remove development tools you use.
Add custom icons to `src/icons/` as needed.

## 🎨 Theming

### Theme Modes

The site supports three theme modes with persistent localStorage:
- **Light** (Sun icon) - Light color scheme
- **Dark** (Moon icon) - Dark color scheme
- **System** (Monitor icon) - Follows OS preference with automatic updates

Theme toggle cycles: Light → Dark → System → Light

User preference is saved and restored on subsequent visits.

### Colors

Theme colors are defined as CSS variables in `src/styles/app.css`:
- Supports light, dark, and system modes
- Colors use HSL format for easy customization
- Variables: `--primary`, `--background`, `--foreground`, `--muted`, etc.

### Fonts

1. Add font files to `/public/fonts/`
2. Define `@font-face` in `src/styles/app.css`
3. Add to `fontFamily` in `tailwind.config.js`
4. Apply to elements or update base layout

### Favicon

All favicon files are located in `/public/favicon/`:
- `favicon-16x16.png` - Standard browser tab icon
- `favicon-32x32.png` - Standard browser tab icon
- `apple-touch-icon.png` - iOS home screen icon (180x180)
- `android-chrome-192x192.png` - Android home screen icon
- `android-chrome-512x512.png` - Android home screen icon (high-res)
- `favicon.ico` - Fallback ICO format
- `site.webmanifest` - Web app manifest for Android

### Theme Toggle

The site supports three theme modes:
- **Light** (Sun icon)
- **Dark** (Moon icon)  
- **System** (Monitor icon) - Follows OS preference

Toggle cycles: Light → Dark → System → Light

User preference is stored in localStorage and persists across sessions.

## 🔧 Configuration

### Astro Config (`astro.config.mjs`)

- **Output mode**: `hybrid` (static generation with selective SSR)
- **Adapter**: Cloudflare Pages
- **Integrations**: MDX, Tailwind, Sitemap, Expressive Code, astro-icon
- **Site URL**: https://rahulk.pages.dev

### Content Schema (`src/content/config.ts`)

Blog posts are validated with Zod:
- `title`: max 60 characters
- `description`: 50-160 characters (SEO optimized)
- `publishDate`: flexible date format
- `tags`: auto-lowercased and deduplicated
- `draft`: boolean (filters from production)

## 📝 Customization Guide

### Skills Section

Edit the skill arrays in `src/pages/index.astro`:
```typescript
const languages = ['Python', 'Django']
const backend = ['REST APIs', 'Celery', 'RabbitMQ']
// ... etc
```

### Experience Cards

Use the `Card` component with consistent structure:
```astro
<Card
  heading='Job Title'
  subheading='Company Name'
  date='Start - End'
>
  <ul class='ml-4 list-disc text-muted-foreground'>
    <li>Achievement or responsibility</li>
  </ul>
</Card>
```

### Navigation

Edit `src/site.config.ts` to modify menu links:
```typescript
export const menuLinks = [
  { title: 'Home', path: '/' },
  { title: 'Blog', path: '/blog/' },
  // Add more links
]
```

## 📦 Key Dependencies

- `astro` - Static site generator
- `@astrojs/mdx` - MDX support
- `@astrojs/tailwind` - Tailwind integration
- `@astrojs/cloudflare` - Cloudflare Pages deployment adapter
- `astro-expressive-code` - Code syntax highlighting
- `astro-icon` - Icon management
- `sharp` - Image processing for favicon generation
- `zod` - Schema validation

## 🚢 Deployment

This site is configured for Cloudflare Pages deployment:

### Automatic Deployment

Push to the `main` branch to trigger automatic deployment to Cloudflare Pages.

### Manual Build

```bash
# Build for production
pnpm build

# Output directory: dist/
```

### Cloudflare Pages Settings

- **Build command**: `pnpm build`
- **Build output directory**: `dist`
- **Node version**: 18+
- **Site URL**: https://rahulk.pages.dev

## 📄 License

This project is based on the Astro Resume template with extensive customizations.

## 🙏 Credits

- **Original Template**: [astro-theme-cactus](https://github.com/chrismwilliams/astro-theme-cactus) for blog design
- **Resume Design**: [minirezume-framer](https://minirezume.framer.website/) for homepage layout
- **Theme Icons**: Inspired by [ibelick/nim](https://github.com/ibelick/nim)
- **Framework**: Built with [Astro](https://astro.build/)
