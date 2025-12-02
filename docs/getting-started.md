# Getting Started

This guide walks you through setting up a new project from this VitePress template and adding your first content.

## Setting Up from Template

1. **Clone and prepare**:
   ```bash
   git clone <your-repo-url> my-new-site
   cd my-new-site
   npm install
   ```

2. **Customize basics**:
   - Update `package.json` with your project name and description.
   - Edit `docs/.vitepress/config.mts` to change the site title and description.

3. **Run locally**:
   ```bash
   npm run docs:dev
   ```
   Visit the local server to see your site.

## Adding New Content

### Creating Pages

1. Create a new Markdown file in `docs/`, e.g., `docs/about.md`:
   ```markdown
   # About Us

   This is our story...
   ```

2. Add frontmatter for metadata:
   ```markdown
   ---
   title: About Us
   description: Learn more about our project
   ---

   # About Us

   Content here...
   ```

### Updating Navigation

Edit `docs/.vitepress/config.mts` to include your new page:

```typescript
sidebar: [
  {
    text: 'Examples',
    items: [
      { text: 'Markdown Examples', link: '/markdown-examples' },
      { text: 'API Examples', link: '/api-examples' },
      { text: 'About', link: '/about' }  // Add this
    ]
  }
]
```

## Customizing the Home Page

The home page is `docs/index.md`. It uses VitePress's home layout with frontmatter:

```yaml
---
layout: home
hero:
  name: "My Project"
  text: "Welcome"
  tagline: A brief description
actions:
  - theme: brand
    text: Get Started
    link: /getting-started
---
```

- **Hero Section**: Update name, text, and tagline.
- **Actions**: Add buttons linking to key pages.
- **Features**: Below the hero, add feature blocks with titles and descriptions.

## Basic Configuration

In `docs/.vitepress/config.mts`:

- **Site Info**: Change `title` and `description`.
- **Navigation**: Update the `nav` array for top menu.
- **Sidebar**: Modify for page organization.
- **Social Links**: Add GitHub, Twitter, etc.

Example:
```typescript
nav: [
  { text: 'Home', link: '/' },
  { text: 'Guide', link: '/getting-started' }
]
```

For more options, see the [VitePress Config Reference](https://vitepress.dev/reference/site-config).