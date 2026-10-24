# Build and deployment

## Branches

`master` contains the editable Jekyll source. `gh-pages` contains only the built
HTML, CSS, JavaScript, images and PDFs that GitHub Pages serves.

The source was recovered from commit
`e9d1e9fd75386e066f1cacaa6abaaf841eefc035` (27 February 2023), immediately
before the last recorded deployment. The recent About, publication, event,
rugby, photo and CV changes have been transferred back into the source.

The restoration branch is based on current GitHub `master`, so merging it keeps
the recent repository history rather than replacing branch history.

## Automatic deployment

`.github/workflows/deploy.yml` builds pull requests and changes to `master`.
It reads `.ruby-version`, installs the exact `Gemfile.lock`, audits the gems,
builds Jekyll, and stores the output as an artifact.

Only successful builds of `master` can publish. The publishing job updates
`gh-pages` with a normal commit, preserving its history and any CNAME file.
It explicitly requests a Pages build and waits for that commit to be published.
Pull requests build and audit without publishing.

GitHub Pages should remain configured as **Deploy from a branch**, branch
**gh-pages**, folder **/(root)**. The workflow does not change repository settings.
Its publishing job requests `contents: write` and `pages: write`; the build job
has only `contents: read`.

## First rollout

1. Review the restored source and local preview.
2. Merge the restoration pull request into `master`.
3. Check the **Build and deploy website** workflow in Actions. Its first run
   validates the Linux build and publishes only after the audit and build pass.
4. Confirm the live About, Publications and CV pages reflect the reviewed preview.
5. Check Dependabot after GitHub processes the new lockfile on the default branch.

After the workflow exists on `master`, a manual rebuild can be requested with
`bin/deploy` (requires GitHub CLI authentication), or with **Run workflow** in
GitHub Actions. The old local script that force-pushed deployment branches has
been replaced by this workflow trigger.

## Updating dependencies

Run `bundle update`, `bundle exec bundler-audit check --update`, and
`bash bin/cibuild`, then inspect the local site before committing the new lockfile.
Dependabot is configured for weekly Ruby and GitHub Actions updates.

The theme itself remains the customized v0.4.1 design. A migration to current
al-folio is a separate change; its newer installation files are not assumed here.
