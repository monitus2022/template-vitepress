# Customization Guide

Learn how to customize themes, add styles, and integrate custom components into your VitePress site.

## Theming and Styling

### Global Styles

Edit `docs/.vitepress/theme/style.css` to override default styles:

```css
/* Custom colors */
:root {
  --vp-c-brand: #646cff;
  --vp-c-brand-light: #747bff;
}

/* Custom fonts */
body {
  font-family: 'Your Font', sans-serif;
}

/* Hide elements */
.vp-sidebar {
  /* Custom sidebar styles */
}
```

### Extending the Theme

Modify `docs/.vitepress/theme/index.ts` to extend the default theme:

```typescript
import DefaultTheme from 'vitepress/theme'

export default {
  extends: DefaultTheme,
  Layout: () => {
    // Custom layout logic
    return h(DefaultTheme.Layout, null, {
      // Add custom slots
    })
  }
}
```

## Adding Custom Components

### Creating Components

1. Create a Vue component in `docs/.vitepress/theme/`, e.g., `MyButton.vue`:

```vue
<template>
  <button class="my-button" @click="$emit('click')">
    <slot />
  </button>
</template>

<script setup lang="ts">
defineProps<{
  variant?: 'primary' | 'secondary'
}>()
</script>

<style scoped>
.my-button {
  padding: 0.5rem 1rem;
  border: none;
  border-radius: 4px;
  background: var(--vp-c-brand);
  color: white;
  cursor: pointer;
}
</style>
```

2. Register in `theme/index.ts`:

```typescript
import MyButton from './MyButton.vue'

export default {
  extends: DefaultTheme,
  enhanceApp({ app }) {
    app.component('MyButton', MyButton)
  }
}
```

### Using Components

Embed in Markdown:

```markdown
<MyButton variant="primary">Click Me</MyButton>
```

Or in theme slots for global elements.

## Advanced Configuration

### Plugins and Features

Add to `docs/.vitepress/config.mts`:

```typescript
export default defineConfig({
  // Search
  themeConfig: {
    search: {
      provider: 'local'
    }
  },

  // Analytics
  head: [
    ['script', { src: 'https://analytics.example.com/script.js' }]
  ]
})
```

### Build Options

Customize the build in `config.mts`:

```typescript
export default defineConfig({
  build: {
    outDir: 'dist',  // Output directory
    sourcemap: true
  }
})
```

For more customization options, see the [VitePress Theme Guide](https://vitepress.dev/guide/theming) and [Extending Default Theme](https://vitepress.dev/guide/extending-default-theme).