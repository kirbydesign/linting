# ![Kirby Design System](assets/kirby-logo.png") Kirby Linting

<!-- Badges section here. -->
[![npm](https://img.shields.io/npm/v/@kirbydesign/linting.svg)](https://www.npmjs.com/package/@kirbydesign/linting)
[![npm](https://img.shields.io/npm/l/@kirbydesign/linting.svg)](https://www.npmjs.com/package/@kirbydesign/linting)
[![npm](https://img.shields.io/npm/dm/@kirbydesign/linting.svg)](https://www.npmjs.com/package/@kirbydesign/linting)

[![GitHub forks](https://img.shields.io/github/forks/kirbydesign/linting.svg?style=social&label=Fork)](https://github.com/kirbydesign/linting/fork)
[![GitHub stars](https://img.shields.io/github/stars/kirbydesign/linting.svg?style=social&label=Star)](https://github.com/kirbydesign/linting/stargazers)

## About
Kirby-linting is an opinionated list of linting rules for the [Kirby Design System](https://github.com/kirbydesign/designsystem).

The "Kirby Linting"-project contains linting rules for the following linting tools:
- [TSLint](https://palantir.github.io/tslint/)
- [Stylelint](https://stylelint.io/)

## Available Scripts

Below is an overview of the scripts available for this project.  
Use them in your terminal like: `npm run <script>`:

| Command | Description |
|---------|-------------|
| `build` | Shortcut for `build:tslint` and `build:stylelint` |
| `build:tslint` | Builds an entire distribution of the **TSLint** linting rules. |
| `build:tslint:src` | Compiles the `.ts`-files, making up the source for the **TSLint** linting rules. |
| `build:tslint:copy-config` | Copies the configuration files, for using the **TSLint** linting rules, to the distribution (`dist`)-folder. |
| `build:tslint:copy-package.json` | Copies the `package.json`-file to the distribution (`dist`)-folder. |
| `clean` | Clears the contents of the distribution (`dist`)-folder. |
| `lint` | Lints the source code. |

*Please note: All of the scripts are listed in the `package.json` file in the `"scripts"` section.*

## TSLint

Using the TSLint rules is a simple matter of adding the package (along with tslint):

```bash
npm install -g tslint shared-tslint-rules
```

...and then adjusting the TSLint configuration (found in `tslint.json`):

```json
{
    "extends": "@kirbydesign/linting/tslint-config",
    "rules": {
        ...
    }
}
```

### TSLint rules

This repository / package provides the following list of rules:

| Rule name | Description |
|-----------|-------------|
| `disallowHttpClientModuleImportInSpecsRule` | Prevents importing `HttpClientModule`, when `HttpClientTestingModule` should used for testing dependencies upon `HttpClientModule` | 
| `disallowSpecificEnvironmentImportRule` | Prevents importing `environment.mock.ts` and `environment.prod.ts`, when `environment.ts` should be used (and selecting the specific version is handled by ng-cli / WebPack) |
| `disallowTnsImportRule` | Prevents importing files ending with `.tns.ts`, when developers should only import `.ts`-file, and allow WebPack to substitute in `.tns.ts` when appropriate |
| `importLineSpacingRule` | Prevents mixing imports from 3rd party libraries with application code, when they should be separated by an empty line |

## Stylelint

### List of Stylelint rules
