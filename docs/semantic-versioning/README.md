# Semantic versioning

[semantic versioning](https://semver.org/), based on [conventional commits](https://conventionalcommits.org/) uses a well defined scheme for versioning software.

A semantic version has the form of `<major>.<minor>.<patch>`, e.g. `1.4.3`, whereas:

- a *major* version indicates incompatible API / application changes -
in an application project often tied to production releases or to indicate different stages in development.
- a *minor* indicates added functionality in a backwards-compatible manner
- a *patch* version indicates the addition of backwards-compatible bug fixes.

## Tools

Tooling support is provided by [standard-version](https://github.com/conventional-changelog/standard-version), that aids the generation of standard versions, including related artifacts like changelog,

## Getting started

```shell
yarn add standard-version --dev # alternatively npm install standard-version --save-dev
```

## Configuration

```json
// package.json
{
  "scripts": {
    "release": "standard-version"
  }
}
```

## Usage examples

```shell
```

Running `yarn release` will automatically:
1. update the `version` field in [package.json](package.json)
2. create a commit (including commit-message following the standard defined [commit messages](#commit-messages))
3. create a tag with version
4. push commit and tag to `remote`

For version detection semantic-version will consider the following commit types:
- `fix` will result in a `patch` version bump
- `feat` will result in a `minor` version bump
- adding `BREAKING CHANGE: <description of breaking change>` will result in a `major` version bump

If necessary (e.g., for applications that usually do not create breaking changes) it is also possible to use `--release-as <major|minor|patch>` to force a `major` bump

## ADR
- [ADR-0004](0004-use-standard-version-for-versioning.md) - Use standard-version for versioning
