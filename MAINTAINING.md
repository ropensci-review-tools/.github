# Notes for maintainers of the peer-review tools

These notes apply to the R packages in this organization that support software peer review, such as pkgcheck, pkgstats, pkgmatch, roreviewapi, srr, repometrics and orgmetrics.
Package-specific maintenance notes live in each package's documentation.

## Local testing

Many of these packages have "extended tests" that only run when this environment variable is set:

```bash
RRT_TEST_ALL=true
```

Maintainers of the whole suite should set it permanently in their `~/.Renviron` file.

## Makefiles

Most repositories include a [Makefile](https://www.gnu.org/software/make/manual/make.html#Introduction).
You use it by typing `make` in a shell, not in an R console.
Typing `make` on its own usually shows a menu of options such as:

```bash
check                Run `rcmdcheck`
doc                  Update package documentation with `roxygen2`
help                 Show this help
pkgcheck             Run `pkgcheck` and print results to screen.
test                 Run test suite
```

There are generally many more. For example, `make doc` runs `roxygenise()` to update all documentation.

## Pre-commit hooks

All repositories also include [pre-commit hooks](https://pre-commit.com), defined in a `.pre-commit-config.yaml` file.
The hooks need to be activated in each local clone by running `precommit::use_precommit()` in its root directory.
See the [precommit package](https://lorenzwalthert.github.io/precommit/) for details.

The `.pre-commit-config.yaml` files should be updated regularly by running the same `precommit::use_precommit()` command.

### What do the hooks do?

The `.pre-commit-config.yaml` files include many standard hooks from the [precommit package](https://lorenzwalthert.github.io/precommit/).
Most repositories also define local hooks at the end of the file, under:

```yaml
repo: local
hooks:
- <hook definition>
```

These call scripts in the `.hooks/` directory, which:

- prevent local commits to the `main` branch if it is protected on GitHub (`no-commit-to-main`);
- enforce increments of a sub-minor `Version:` in the package `DESCRIPTION` file (`description`). Each commit is then identified by a unique version number, like `1.2.3.015`, which denotes the 15th commit to version `1.2.3`;
- ensure that README badges for GitHub workflows exactly match the workflow names (`workflow-badges`).
