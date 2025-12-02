# Deployment

Deploy your VitePress site to Cloudflare Pages for fast, global hosting.

## Build Preparation

Before deploying, build your site:

```bash
npm run docs:build
```

This generates static files in `docs/.vitepress/dist`.

## Cloudflare Pages Setup

1. **Connect Repository**:
   - Go to [Cloudflare Pages](https://pages.cloudflare.com/).
   - Click "Create a project" > "Connect to Git".
   - Select your GitHub repository.

2. **Configure Build Settings**:
   - **Build command**: `npm run docs:build`
   - **Build output directory**: `docs/.vitepress/dist`
   - **Root directory**: `/` (leave as default)
   - Add environment variables if needed (e.g., `NODE_VERSION: 18`).

3. **Deploy**:
   - Click "Save and Deploy".
   - Cloudflare will build and deploy your site.
   - Auto-deploys on future pushes to the main branch.

## Custom Domain

1. In Cloudflare Pages dashboard, go to your project > "Custom domains".
2. Add your domain and follow DNS setup instructions.
3. Update DNS records as prompted.

## Troubleshooting

- **Build Failures**: Check build logs in Cloudflare dashboard. Ensure dependencies are in `package.json`.
- **404 Errors**: Verify build output directory is correct (`docs/.vitepress/dist`).
- **Caching Issues**: Purge cache in Cloudflare dashboard if changes don't appear.
- **Environment Variables**: Use for sensitive data; restart builds after adding.

For more details, see [Cloudflare Pages Docs](https://developers.cloudflare.com/pages/).