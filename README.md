# sanger-data-management-lib
A Python library for data and metadata management (Wellcome Sanger Institute)

## Scope

- Data and metadata import (e.g. from scientific instruments, external resources)
- Data and metadata maintenance
- Data and metadata export and archival

## Development

### CI

- [basedpyright](https://pypi.org/project/basedpyright/) is run for static type checking in CI 
- [Black](https://pypi.org/project/black/) is run for uninform code formatting.
- [pytest](https://pypi.org/project/pytest/) is run for the main test suite and [pytest-it](https://pypi.org/project/pytest-it/) annotations are available to document the purpose of each test.

### Releases

- Release version strings should use [SemVer](https://semver.org/) so that we signal roughly how much a release has changed the library behaviour.
- The library version is taken from the most recent git tag and stored in the Python package metadata. As the version string is taken directly from the tag with no modification, please do not prefix the tag with the letter `v` e.g. `v1.2.0`.
- Automated releases are created when a git tag is pushed. The release will include generated release notes by default (these may be edited if required).

```shell
# Example release from the command line

# Update the devel branch to get the changes for release
$ git checkout devel
$ git pull

# Switch to the master branch
$ git checkout master

# Merge the changes from devel into master
$ git merge devel

# Create an annotated tag with message and tag string both set to the release version 
$ git tag -a 1.2.3 -m 1.2.3

# Push the changes and tag, triggering CI to build a release
$ git push --tags origin master
```
