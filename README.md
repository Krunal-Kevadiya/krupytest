# KrupyTest - the automated code prettifier

Are you tired of configuring `.pre-commit-config.yaml` all over your projects, and
keeping those up-to-date?

Me too. 🤦‍

Thus, here's krupytest. It uses [Krupy][] to keep your projects updated with the
latest code formatters and linters.

[krupy]: https://krupy.readthedocs.io/

## 1st usage

1. [Install krupy](https://krupy.readthedocs.io/en/stable/#installation)
1. [Install pre-commit](https://pre-commit.com/#install)
1. Enter your project folder: `cd my-project`
1. Make it a git repo: `git init`
1. Run `krupy copy https://github.com/Krunal-Kevadiya/krupytest.git .`
1. Answer questions
1. Activate pre-commit: `pre-commit install`
1. Commit: `git commit -am 'Apply autoprettier'` (repeat if pre-commit reformats
   anything and makes the update fail)
1. Update your code `pre-commit run -a`
1. Commit: `git commit -am 'Run pre-commit'`

## Get updates

1. Enter your project folder: `cd my-project`
1. Update: `krupy -a .krupy-answers.krupytest.yml update`
1. Answer questions, if anything changed
1. Commit: `git commit -am 'Update autoprettier'` (repeat if pre-commit reformats
   anything and makes the update fail)
1. Update your code `pre-commit run -a`
1. Commit: `git commit -am 'Run pre-commit'`

## Notes for template maintainers

This template is self-applied, and as you can imagine, there are some 🐔+🥚 situations.

To update it:

1. Publish a new release on Github
1. `git fetch --tags`
1. `krupy -a .krupy-answers.krupytest.yml --prereleases update`

In case you want to self-test a new release locally:

1. `git tag v0.1.0a99` ... or the version that you will release.
1. `krupy -a .krupy-answers.krupytest.yml --prereleases update`
1. Once you're happy: `git tag -d v0.1.0a99`
1. Open PR.
1. Merge it.
1. Release.
1. Do the proper update.

At some point, this should be automated easily.
