# Contributing to USWDS

What it's like to work with and contribute to the
[USWDS](https://github.com/uswds/uswds) framework.

## Repo's you should know
When you visit the [USWDS organization](https://github.com/uswds) you'll find a bunch of repo's.


As a dev, you'll mostly be working in:
- [USWDS](https://github.com/uswds/uswds)

  Where the actual framework code lives.
- [USWDS-Site](https://github.com/uswds/uswds-site)

  The site code for the [website](https://designsystem.digital.gov/)

- [USWDS Gulp](https://github.com/uswds/uswds-gulp)

  Helps dev get set up locally to compile and use the framework. In case they don't have a local build system or don't want to be bothered creating one.

- [USWDS for Designers](https://github.com/uswds/uswds-for-designers)

  Occasionally you'll need to pull and review the Sketch file to make sure everything syncs up with component development.


## The framework (USWDS)

Where things live and what they are.

### File structure

```
.
├── .circleci
├── .github
├── config/
├── docs/
├── examples/
├── spec/
├── src/
├── .browserslistsrc
├── .codeclimate.yml
├── .editorconfig
├── .eslintignore
├── .eslintrc.yml
├── .gitignore
├── .npmignore
├── .nvmrc
├── .prettierignore
├── .snyk
├── .stylelintrc.json
├── CONTRIBUTING.md
├── LICENSE.md
├── README.md
├── _config.yml
├── fractal.config.js
├── gulpfile
├── package-lock.json
├── package.json
└── tsconfig.json
```
There are a few standout directories that you should know. They are listed below.

#### config

Holds the gulp tasks that `gulpfile.js` consumes. Also has a `nycrc.yml` file, but not sure what that does.

#### docs
Holds who is using uswds, but this seems to be outdated and no longer maintained.

> We should update this directory to give users the best possible documentation.

#### examples
How USWDS lives alongside other tech. There's an existing [angular](https://github.com/uswds/uswds/issues/3341) setup that might be worth importing.

> Also needs updating.

#### spec

Most things related to testing. Our unit tests, visual regression screenshots, and accessibility testing, and our setup for a headless chrome instance live here.

> We should organize this.

#### src
The framework source code. Fonts, img, js, stylesheets get compiled and built out into a `dist/` folder that users and themers  recognize.

The other directories are for internal use, they are:

##### data

Color tokens used in SASS.

##### components
Component code (nunjucks files) that Fractal (component library) will consume to display components. These compiled components will also be fed to USWDS-Site. Here's an example of [that](https://github.com/uswds/uswds-site/blob/b17f6da97fff8a6358c190e266878a021f3f5b55/_includes/code/components/card.html#L4). Which gets used in the documentation page of the [card](https://github.com/uswds/uswds-site/commit/1a078913d35473982dcdafec1301db48193e8c0e#diff-a4c5956cc2ee5dc95b24edcbf09a7cfcR13).

### Git conventions

### CI Process

Tasks are defined in `.circleci` directory. When you commit and submit PR's to USWDS and USWDS-Site you'll see some checks are run. If they're all green then your PR should be good to review and merge. If not, you have to resolve the errors before.

![](./images/uswds-checks.png)

#### circle-uswds
Checks for build errors.

#### federalist/build
Will give you a preview link for fractal (component library) like [this ↗](https://federalist-3b6ba08e-0df4-44c9-ac73-6fc193b0e19c.app.cloud.gov/preview/uswds/uswds/jm-component-breadcrumb/components/detail/breadcrumb--default.html) or a preview of the website with your changes like [here ↗](https://federalist-ead78f8d-8948-417c-a957-c21ec5617a57.app.cloud.gov/preview/uswds/uswds-site/jm-card-component-docs/components/card/).

#### security/snyk
A plugin we use to scan for vulnerabilities in our dependencies. These checks usually pass if you keep your dependencies up-to-date. In the rare cases there are no patches available you can opt to ignore warnings for 30 days, but speak to someone first.

## Creating Issues

## Developing Components

## USWDS Site

## Releasing
