## Developing

### [! WIP !] Branching

This repository has 3 functional branches:

1. `main`: contains all the logic for running the site
2. `gh-pages`: site source that will automatically be deployed to GitHub Pages by a GitHub-owned bot whenever there is a push
3. `gh-pages-main`: site source that the developer edits where changes will be transformed by automation and pushed to `gh-pages`

2self: this is probably an all around better strategy so I can place automation/steps to transform local -> remote (though this should remain vvv close; would
be useful for things like redirecting to the resource in all 3 cases: 1) /about 2) /about/ and 3) /about.html
with just haveing about.md in the root directory (and for others in nested directories))
would also be where you can run test CI/CD.

... this ^ might just be `main`? it only contains the logic for getting data that runs the site. would also be where 

### [! /WIP !]

### Site URLs

Remote: https://cawfeecake.github.io/avwx-report/

Local: http://127.0.0.1:4000/avwx-report/

### Launch a local instance

```bash
# on branch "gh-pages"
bundle exec jekyll build && bundle exec jekyll serve`
```

### Differences between local instance and site on GitHub Pages

* The trailing `/` is required when accessing the root of the site on local (i.e. http://127.0.0.1:4000/avwx-report returns a 404),
but on GitHub Pages it will redirect from https://cawfeecake.github.io/avwx-report to https://cawfeecake.github.io/avwx-report/

* On GitHub Pages a 404 will be returned when a trailing `/` is added to the end of non-root page URLs, but on local it will accept
both cases (trailing `/` or not)
