# Smart Home Journal

A plain Hugo blog. You write Markdown, push to GitHub, and the site publishes itself.

## One-time setup

1. **Install Hugo** (WSL/Linux): download the latest `hugo_*_linux-amd64.deb` from
   https://github.com/gohugoio/hugo/releases and run `sudo dpkg -i hugo_*_linux-amd64.deb`.
   Skip `apt install hugo`, because Ubuntu's package is usually outdated.
   If your theme uses Sass/SCSS, also install Dart Sass (see the theme's README).
2. **Create the repo**
   ```sh
   git init -b main
   git add .
   git commit -m "Initial skeleton"
   git remote add origin git@github.com:<you>/<repo>.git
   git push -u origin main
   ```
3. **Turn on Pages:** in the repo, go to Settings → Pages → Source and choose **GitHub Actions**.
   From then on, every push to `main` publishes the site.

## Picking a theme

Browse https://themes.gohugo.io. Every theme there has a live demo. Once you've picked one:

```sh
git submodule add <theme-repo-url> themes/<ThemeName>
```

Then set `theme = "<ThemeName>"` in `hugo.toml`. Themes also have their own optional settings
(dark mode, social links and so on), which go under `[params]`. Check the theme's README for those.

To switch themes later, add the new one the same way and change that single line. Your posts stay as they are.

## Writing

```sh
hugo new content posts/cabling-before-plaster/index.md   # new draft from the template
hugo server -D                                            # live preview at http://localhost:1313 (-D includes drafts)
```

- Each post is a folder. Put the photos for a post in the same folder as its `index.md`.
- Set `draft: false` when a post is ready, then commit and push.
- **categories** = renovation phase, **tags** = rooms and tech, **series** = multi-part builds.
  The theme builds the listing pages for these automatically.

The template's section headings (problem, what I did, what went wrong, cost, WAF verdict) are only prompts.
Delete whatever doesn't fit a post.
