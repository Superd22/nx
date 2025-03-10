The Nx Plugin for Angular contains executors, generators, and utilities for managing Angular applications and libraries
within an Nx workspace. It provides:

- Integration with libraries such as Storybook, Jest and Cypress.
- Generators to help scaffold code quickly, including:
  - Micro Frontends
  - Libraries, both internal to your codebase and publishable to npm
  - Upgrading AngularJS applications
  - Single Component Application Modules (SCAMs)
- NgRx helpers.
- Utilities for automatic workspace refactoring.

{% callout type="note" title="Currently using the Angular CLI?" %}
You can easily and mostly **automatically migrate from an Angular CLI** project to Nx! Learn
more [here](/recipes/angular/migration/angular).
{% /callout %}

## Setting up the Angular plugin

{% callout type="note" title="Keep Nx Package Versions In Sync" %}
Make sure to install the `@nx/angular` version that matches the version of `nx` in your repository. If the version numbers get out of sync, you can encounter some difficult to debug errors. You can [fix Nx version mismatches with this recipe](/recipes/tips-n-tricks/keep-nx-versions-in-sync).
{% /callout %}

Adding the Angular plugin to an existing Nx workspace can be done with the following:

```shell
yarn add -D @nx/angular
```

```shell
npm install -D @nx/angular
```

## Using the Angular Plugin

### Generating an application

It's straightforward to generate an Angular application:

```shell
nx g @nx/angular:app appName
```

By default, the application will be generated with:

- ESLint as the linter.
- Jest as the unit test runner.
- Cypress as the E2E test runner.

We can then serve, build, test, lint, and run e2e tests on the application with the following commands:

```shell
nx serve appName
nx build appName
nx test appName
nx lint appName
nx e2e appName
```

### Generating a library

Generating an Angular library is very similar to generating an application:

```shell
nx g @nx/angular:lib libName
```

By default, the library will be generated with:

- ESLint as the linter.
- Jest as the unit test runner.

We can then test and lint the library with the following commands:

```shell
nx test libName
nx lint libName
```

Read more about:

- [Creating Libraries](/concepts/more-concepts/creating-libraries)
- [Library Types](/concepts/more-concepts/library-types)
- [Buildable and Publishable Libraries](/concepts/more-concepts/buildable-and-publishable-libraries)

### Fallback to `@schematics/angular`

If you try to invoke a generator that is not present in `@nx/angular`, the request will automatically be forwarded on
to `@schematics/angular`. So, even though there is no `@nx/angular:service` generator, the following command will
successfully create a service:

```shell
nx g @nx/angular:service my-service
```

## More Documentation

- [Angular Nx Tutorial](/getting-started/tutorials/angular-monorepo-tutorial)
- [Migrating from the Angular CLI](/recipes/angular/migration/angular)
- [Setup Module Federation with Angular and Nx](/concepts/more-concepts/faster-builds-with-module-federation)
- [Upgrading an AngularJS application to Angular](/recipes/angular/migration/angularjs)
- [Using Tailwind CSS with Angular projects](/recipes/angular/using-tailwind-css-with-angular-projects)
