# Tooling + Best practices

This file repository collects a number of tools and best practices recommended for use in new and existing projects.

**Note** This repository uses [lightweight architectural deicions records](docs/adr) to document background information on the tools recommended in this project.
See [adr folder](docs/adr) for aditional overview over the tools and best practices added.

## Tools

### husky

[husky](https://github.com/typicode/husky) provides an easy an solution to handling commit hooks.

husky provides:

* and auto installer to ensure availabilty of git hooks for all developers without the need for additional documentation
* [easy configuration](https://github.com/typicode/husky/blob/dev/docs.md)

**installation**

```shell
yarn add husky --dev # alternatively npm install husky --save-dev
```

**configuration examples**

```json
// package.json
{
  "husky": {
    "hooks": {
      "pre-commit": "npm run commitlint",
      "pre-push": "npm lint"
    }
  }
}
```

## Commit messages

Commit messages should generally follow a format agreed within the development team to ensure consistency and clarity on how to write a commit.

This guide recommends using a format based on [Google's Angular developer's guidelines](https://github.com/angular/angular/blob/master/CONTRIBUTING.md#commit), using a format of:

```shell
git commit -m "type(module-name): imperative, present tense description of commit #ticket"
```

with those types:

  - feat: describes a product feature added by this commit as well as detectable improvements made to existing modules or components
  - fix: describes a bugfix, i.e., some correction to an existing module or component
  - docs: describes a commit purely for documentation purposes
  - style: describes changes that do not effect the functionality of the code, e.g., linting or code style improvements
  - refactor: describes a refactoring of existing code
  - chore: describes changes made to the infrastructure of the project, e.g., configuration or build jobs
  - revert: reverts a previous commit
  - test: a commit purely to for testing purposes without functional impact

Tool support is available through [commitizen](https://github.com/commitizen/cz-cli) (cli-tool) and [commitlint](https://github.com/marionebl/commitlint) (lints commits).

**installation**

```shell
yarn add commitizen commitlint cz-customizable --dev
  # alternatively: npm install commitizen commitlint cz-customizable --save-dev
```

**usage example**

```shell
git commit -m "feat(button): adds button component #pr-123"

# alternatively:
# create a new commit with help of cli / prompt tool:
yarn commit # alternatively: npm run commit
```

