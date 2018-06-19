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

