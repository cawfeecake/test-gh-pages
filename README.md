## Developing
When the site is built locally using:
```bash
# on branch "gh-pages"
bundle exec jekyll build && bundle exec jekyll serve`
```
the url `https://cawfeecake.github.io/test-gh-pages` will direct to a 404 b/c the local jekyll
requires the trailing `/` at the end. This is not an issue when the site is deploy to GitHub Pages
(i.e. `https://cawfeecake.github.io/test-gh-pages` directs to `https://cawfeecake.github.io/test-gh-pages/`
with no issue)
