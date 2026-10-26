# Jim Boelrijk's website

Jekyll source for [jimbo994.github.io](https://jimbo994.github.io), based on the
customized al-folio v0.4.1 theme. The original design is retained; the build uses
Ruby 3.4 and Jekyll 4.4 with an updated, audited dependency lockfile.

## Local preview

Use the Ruby version in `.ruby-version`. On this Mac, Homebrew Ruby 3.4 is installed:

```bash
export PATH="/opt/homebrew/opt/ruby@3.4/bin:$PATH"
bundle config set --local path vendor/bundle
bundle install
bin/serve
```

Open <http://localhost:4000>. Jekyll rebuilds when source files change.

## Edit content

- About: `_pages/about.md`; talks and rugby highlights: `_includes/profile-highlights.html`.
- Publications: `_bibliography/papers.bib`; year groups: `_pages/publications.md`.
- Publication presentation: `_layouts/bib.html` and `_sass/_custom.scss`.
- Profile photo: `assets/img/prof_pic.jpg`.
- Downloadable CV: `assets/pdf/CV_website.pdf`; CV page: `_pages/cv.md`.
- Shared navigation, metadata and settings: `_config.yml` and `_includes/`.
- Archived teaching and supervision (hidden from navigation): `_pages/teaching.md` and `_projects/`.

### Update the public CV

The public download uses the general CV from the adjacent `CV` checkout:
`main3_fancy_onecolumn.tex`. After editing that source, compile it and copy the
result into this repository:

```bash
cd ../CV
tectonic --outdir output/pdf main3_fancy_onecolumn.tex
cp output/pdf/main3_fancy_onecolumn.pdf ../Jimbo994.github.io/assets/pdf/CV_website.pdf
```

Update `cv_updated` in `_pages/cv.md` when replacing the PDF. The embedded preview
and download share the same PDF URL, with a build version to refresh cached copies.

## Build and audit

```bash
bundle exec bundler-audit check --update
bash bin/cibuild
```

The generated website is written to `_site/`, which is ignored by Git.
Commit editable source and `Gemfile.lock` to `master`; deployment writes the
generated files to `gh-pages`. See [DEPLOYMENT.md](DEPLOYMENT.md).
