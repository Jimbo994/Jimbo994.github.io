# Dependency review

Reviewed on 24 October 2026 against the repository's 39 open Dependabot alerts.
The new lockfile addresses every affected version range in that snapshot:

| Dependency | Restored build |
| --- | --- |
| Active Support | 8.1.4 |
| Addressable | 2.9.0 |
| Concurrent Ruby | 1.3.8 |
| Nokogiri | 1.19.4 |
| REXML | 3.4.4 |
| WEBrick | 1.9.2 |
| HTTParty, Loofah, Crass | Removed with the unused demo RSS importer |

`bundle exec bundler-audit check --update` reported **No vulnerabilities found**
using ruby-advisory-db commit `03da937a9e171e3fedebde6620e203559b7a60c0`.
The current GitHub alert ranges were also compared directly with the resolved gems.
This is a dated dependency review, not a guarantee against future vulnerabilities.

The build no longer installs unused diagram, image-conversion, Twitter or
JavaScript-minification plugins. Publication figures and other static images
are retained. The browser's obsolete polyfill.io script has been removed.

GitHub's alerts remain open until these changes reach the default branch and
GitHub rescans the dependencies. No alerts have been dismissed manually.
Both CI and local development can run the dependency audit above.

This review covers Ruby build dependencies. CDN-hosted browser libraries are
separate dependencies and should also be reviewed when updating the theme.
