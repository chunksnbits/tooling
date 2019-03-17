
# Git Commit linting
Commit messages should generally follow a format agreed within the development team to ensure consistency and clarity on how to write a commit.

This guide recommends using a format based on [Google's Angular developer's guidelines](https://github.com/angular/angular/blob/master/CONTRIBUTING.md#commit), using a format of:

```shell
git commit -m "type(module-name): imperative, present tense description of commit #ticket"
```

with types:

  - feat: describes a product feature added by this commit as well as detectable improvements made to existing modules or components
  - fix: describes a bugfix, i.e., some correction to an existing module or component
  - docs: describes a commit purely for documentation purposes
  - style: describes changes that do not effect the functionality of the code, e.g., linting or code style improvements
  - refactor: describes a refactoring of existing code
  - chore: describes changes made to the infrastructure of the project, e.g., configuration or build jobs
  - revert: reverts a previous commit
  - test: a commit purely to for testing purposes without functional impact

## Tools

Integration can be done with:
- [commitizen](https://github.com/commitizen/cz-cli) (cli-tool) and
- [commitlint](https://github.com/marionebl/commitlint) (lints commits).

See respective Github projects for more details.

## Getting started

```shell
npm install commitizen commitlint cz-customizable --save-dev
# or
yarn add commitizen commitlint cz-customizable --dev
```

## Configuration

```json
// package.json
{
  "config": {
    "commitizen": {
      "path": "node_modules/cz-customizable"
    },
    "cz-customizable": {
      "config": ".cz-config.js"
    }
  }
}
```

```js
// .cz-config.js
module.exports = {
	allowBreakingChanges: ['feat', 'fix'],
	allowCustomScopes: true,
	scopes: ['system'],
	types: [
		{ value: 'feat', name: 'feat:     A new feature' },
    ...
  ]
};
```

## Usage examples

```shell
git commit -m "feat(button): adds button component #pr-123"

# alternatively:
# create a new commit with help of cli / prompt tool:
yarn commit # alternatively: npm run commit
```

## ADR
- [ADR-0003](0003-use-commitizen-commitlint.md) - Use commitizen and commitlint for git commits