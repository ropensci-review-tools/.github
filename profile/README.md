:wave: Welcome to the rOpenSci Project on GitHub. Our repositories are currently distributed across a few different organizations.

You can explore our [resources page](https://ropensci.org/resources) to find what you're after, it includes a list of all our GitHub organizations.

Also refer to our [code of conduct](https://ropensci.org/code-of-conduct/).

## Tools for software peer review

This organization contains packages and services developed to support [rOpenSci's software peer review](https://ropensci.org/software-review/), including the review of [statistical software](https://stats-devguide.ropensci.org).
Each package has its own documentation website, linked below.
The organization also hosts other rOpenSci repositories that are not related to peer review, such as tools for translation.

### For package authors

- [**pkgcheck**](https://docs.ropensci.org/pkgcheck/) checks whether a package is ready to be submitted. Authors should only need the one function, [`pkgcheck()`](https://docs.ropensci.org/pkgcheck/reference/pkgcheck.html). [**pkgcheck-action**](https://github.com/ropensci-review-tools/pkgcheck-action) runs it as a GitHub Action.
- [**srr**](https://docs.ropensci.org/srr/) helps authors document compliance with our [standards for statistical software](https://stats-devguide.ropensci.org/standards.html) within their code. Its website includes [a demonstration to walk through](https://docs.ropensci.org/srr/articles/srr-stats.html).
- [**goodpractice**](https://docs.ropensci.org/goodpractice/) gives advice on R package building.

### Infrastructure behind the review process

- [**roreviewapi**](https://docs.ropensci.org/roreviewapi/) is the API behind [`ropensci-review-bot`](https://github.com/ropensci-review-bot). Its vignettes document server setup, endpoints and debugging.
- [**pkgstats**](https://docs.ropensci.org/pkgstats/) does static code analysis of R packages and is used by pkgcheck. [**mirrors**](https://github.com/ropensci-review-tools/mirrors) holds scripts to mirror CRAN, rOpenSci and Bioconductor sources for pkgstats and pkgmatch data.
- [**pkgmatch**](https://docs.ropensci.org/pkgmatch/) finds R packages that match a description or another package.
- [**dashboard**](https://dashboard.ropensci.org/) is the dashboard for software peer review.
- [**repometrics**](https://docs.ropensci.org/repometrics/) and [**orgmetrics**](https://docs.ropensci.org/orgmetrics/) compute metrics for repositories and organizations ([rOpenSci's metrics dashboard](https://metrics.ropensci.org/)).

Maintainers: see the [notes on local testing, Makefiles and pre-commit hooks](https://github.com/ropensci-review-tools/.github/blob/main/MAINTAINING.md).
