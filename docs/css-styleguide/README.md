
# CSS styleguide
CSS styles (including flavours like SCSS, Sass or Less) can be hard to keep consistend in a project team with mixed experiences and fluctuating members.

Beteween the available flavours I favour  [BEM](http://getbem.com/introduction/) css style, due to its well defined rules and wide adoption

## Tools
[stylelint](https://github.com/stylelint/stylelint) allows linting of CSS files and most common flavours.

It can be integrated into the development setup and finds support in most common IDEs, e.g.:
- [VSCode](https://github.com/shinnn/vscode-stylelint)
- [IntelliJ](https://plugins.jetbrains.com/plugin/9276-intellij-stylelint-plugin)
- [Atom](https://atom.io/packages/linter-stylelint)

## Getting started
```shell
npm install stylelint stylelint-config-standard stylelint-selector-bem-pattern --save-dev
# or
yarn add --dev stylelint stylelint-config-standard stylelint-selector-bem-pattern
```

## Configuration
```json
// .stylelintrc
{
  "extends": "stylelint-config-standard",
  "plugins": [
    "stylelint-selector-bem-pattern"
  ],
  "rules": {
    "...": "custom other rules"
  }
}
```

see:
* [User guide](https://github.com/stylelint/stylelint/blob/master/docs/user-guide.md) for an overview of availables rules, plugins and usage examples
* [Rules](https://github.com/stylelint/stylelint/blob/master/docs/user-guide/rules.md) for an overview of default rules

## Usage examples
Run manually using the CLI:

``` shell
yarn stylelint 'src/**/*.scss'
```

I also recommend adding stylelint to either developers or Git workflow, e.g.: defining a husky `pre-push` hook
``` json
{
  ...
  "hooks": {
    "pre-push": "stylelint 'src/**/*.scss'"
  }
}
```

## ADR
- [ADR-0008](0008-use-linter-for-css.md) - Use linter for CSS
