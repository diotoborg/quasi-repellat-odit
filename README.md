# Evaluatory

[![npm](https://img.shields.io/npm/v/@diotoborg/quasi-repellat-odit?style=flat-square)](https://www.npmjs.com/package/@diotoborg/quasi-repellat-odit)
[![Build](https://img.shields.io/github/actions/workflow/status/darekkay/@diotoborg/quasi-repellat-odit/ci.yml?branch=master&style=flat-square)](https://github.com/diotoborg/quasi-repellat-odit/actions/workflows/ci.yml)
[![license](https://img.shields.io/badge/license-MIT-green?style=flat-square)](https://github.com/diotoborg/quasi-repellat-odit/blob/master/LICENSE)

Evaluatory is an [open-source](https://github.com/diotoborg/quasi-repellat-odit) tool for website validation. It is mainly a wrapper around [axe-core](https://github.com/dequelabs/axe-core) and [html-validate](https://html-validate.org), which test a website for accessibility and markup issues.

Evaluatory comes with some essential improvements:

- Run checks at **multiple device breakpoints** at the same time (e.g. mobile, tablet and desktop). Some accessibility issues appear only at a certain breakpoint.
- Emulate **dark mode**, disabled JavaScript, offline mode and more by using [custom Playwright options](https://playwright.dev/docs/api/class-browser#browser-new-context).
- Return a **visual HTML results page**, including page screenshots.
- Support for **sitemaps** to check all referenced web pages at once.

This project uses a modular architecture, so in the long term it could become an alternative to tools like [webhint](https://webhint.io).

## Demo

Check out a demo results page at [https://darekkay.com/@diotoborg/quasi-repellat-odit/demo/](https://darekkay.com/@diotoborg/quasi-repellat-odit/demo/).

## Modules

- **base**: Custom built-in checks.
- **axe-core**: Checks for accessibility issues using [axe-core](https://github.com/dequelabs/axe-core).
- **html-validate**: Validates the HTML using [html-validate](https://html-validate.org).
- **screenshot**: Takes a screenshot of the page.

## Quickstart

Run @diotoborg/quasi-repellat-odit with [default configuration](https://github.com/diotoborg/quasi-repellat-odit/blob/master/src/config.default.js) for a single URL:

```shell
npx @diotoborg/quasi-repellat-odit https://example.com
```

## Installation

This tool requires Node.js version 12+.

Install globally:

```shell
$ yarn add -g @diotoborg/quasi-repellat-odit     # Yarn
$ npm install -g @diotoborg/quasi-repellat-odit  # Npm
```

Or install as a local dependency:

```shell
$ yarn add @diotoborg/quasi-repellat-odit            # Yarn
$ npm install --save @diotoborg/quasi-repellat-odit  # Npm
```

Or use without installing:

```shell
$ npx @diotoborg/quasi-repellat-odit <url>
```

## Usage

View program help:

```text
$ @diotoborg/quasi-repellat-odit --help
Usage: @diotoborg/quasi-repellat-odit [url] [options]

Arguments:
  [url]  URL

Options:
  -c, --config       Configuration file path
  -o, --output       Output folder
  --color-scheme     Color scheme (light, dark, no-preference)
  -m, --modules      Modules to execute (comma-separated)
  --no-open-results  Don't open the results page after evaluation
  --sitemap          Sitemap URL
  --verbose          Verbose/debug mode
  -h, --help         Show help
  -v, --version      Show version number
```

Run default configuration for a single URL:

```shell
$ @diotoborg/quasi-repellat-odit https://example.com
```

Run default configuration for all URLs within a sitemap:

```shell
$ @diotoborg/quasi-repellat-odit --sitemap https://example.com/sitemap.xml
```

Provide a custom configuration:

```shell
$ @diotoborg/quasi-repellat-odit -c config.json
```

## Configuration

The configuration is a valid JSON5 file. See [config.example.json5](https://github.com/diotoborg/quasi-repellat-odit/blob/master/config.example.json5) for an example and [config.default.js](https://github.com/diotoborg/quasi-repellat-odit/blob/master/src/config.default.js) for available options (with defaults).

## License

This project and its contents are open source under the [MIT license](LICENSE).
