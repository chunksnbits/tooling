
# Git commit hooks
The use of git commit hooks allows to ensure coding standard before merging changes into the development or master branch. In general hooks are advisable for:

* linting(*)
* testing(*)
* commit messages

(*) can be moved to other parts of the development stack, e.g., onto a Jenkins or Gitlabs task runner, depending on setup

## Tools
[husky](https://github.com/typicode/husky) simplifies integration and configuration of commit hooks into npm packages.

See [documentation](https://github.com/typicode/husky/blob/dev/docs.md) for more details on how to use

## Getting started
```shell
npm install husky --save-dev
# or
yarn add husky --dev
```

## Configuration
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

## Usage examples
The git commit hooks will automatically be applied, when you run the corresponding hooks, e.g.:

``` shell
git commit -m "feat: adds awesome"

husky > commit-msg (node v9.11.2)
yarn run v1.13.0
warning ../package.json: No license field
$ commitlint -e $GIT_PARAMS

⧗   input: feat: adds awesome
✔   found 0 problems, 0 warnings
    (Need help? -> https://github.com/conventional-changelog/commitlint#what-is-commitlint )


✨  Done in 0.81s.
```

## ADR
- [ADR-0002](0002-use-husky-for-git-hooks.md) - Use husky for git hooks
