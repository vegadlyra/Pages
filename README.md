# Host a page for WordPress

This repository publishes the files in `site/` as a static website with GitHub
Pages. Host a standalone HTML page and its assets here, then show it in a
WordPress page using an iframe.

## Publish the page

1. In the repository, open **Settings → Pages** and set **Build and deployment
   → Source** to **GitHub Actions**.
2. Your supplied page is already at `site/index.html`. Replace that file to
   update the page. Add any images, stylesheets, or scripts under `site/` and
   reference them with relative paths.
3. Commit and push your changes to `main`. The **Deploy GitHub Pages** workflow
   will publish the contents of `site/`. You can also start it from the
   repository's **Actions** tab.
4. Open the completed workflow run to find the published page URL.

The URL normally looks like
`https://<owner>.github.io/<repository>/`. Replace the placeholders with this
repository's owner and name.

## Embed it in WordPress

Add a **Custom HTML** block to your WordPress page and paste this snippet,
replacing the URL with the published URL from the workflow:

```html
<iframe
  src="https://<owner>.github.io/<repository>/"
  title="Embedded page"
  width="100%"
  height="700"
  style="border: 0;"
  loading="lazy">
</iframe>
```

Adjust `height` to fit your page. WordPress may restrict iframes for users
without permission to add unfiltered HTML; if it removes the iframe, ask your
site administrator to allow it or use an iframe plugin.
