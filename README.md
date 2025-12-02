# VitePress Template

A minimal template for creating websites with VitePress. This repo provides a starting point for building documentation sites or simple web projects using VitePress's static site generator.

## Prerequisites

- Node.js (version 16 or higher)
- npm or yarn

## Quick Start

1. **Clone the repository**:
   ```bash
   git clone <your-repo-url> my-project
   cd my-project
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Run the development server**:
   ```bash
   npm run docs:dev
   ```
   Open [http://localhost:5173](http://localhost:5173) to view the site.

4. **Build for production**:
   ```bash
   npm run docs:build
   npm run docs:preview
   ```

## Project Structure

- `docs/` - Source files for the website content (Markdown pages)
- `docs/.vitepress/` - VitePress configuration and theme files
  - `config.mts` - Site configuration (navigation, sidebar, etc.)
  - `theme/` - Custom theme files (styles and components)
- `package.json` - Project dependencies and scripts

## Customization Quick Reference

- **Home Page**: Edit `docs/index.md` to customize the hero section, features, and actions.
- **Navigation & Sidebar**: Modify `docs/.vitepress/config.mts` to update menus and links.
- **Content**: Add new `.md` files in `docs/` and link them in the config.
- **Theming**: Update `docs/.vitepress/theme/style.css` for styles or extend `theme/index.ts` for components.
- **Deployment**: See `docs/deployment.md` for Cloudflare Pages setup.

For detailed guides, visit the [Getting Started](docs/getting-started.md) and [Customization](docs/customization.md) pages on the site.

## Scripts

- `npm run docs:dev` - Start development server
- `npm run docs:build` - Build for production
- `npm run docs:preview` - Preview production build locally

## License

[Add your license here]
