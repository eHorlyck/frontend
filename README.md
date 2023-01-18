# LCA Collect

LCA Collect is a web platform for collecting documentation for LCA (Life Cycle Assessment).
LCA Collect has been developed by [Arkitema](https://arkitema.com) and [COWI](https://cowi.com) and given to the Danish
Building Industry to be used widely in the industry.

## Introduction

This the frontend app for the LCA Collect Tool.
It is written in Typescript and React.

## Get started

Copy the `.env.example` to `.env` and populate the values.

To start the dev server
`npm run dev`

To run unit tests
`npm run test`

To run interactive Cypress tests
`npm run e2e:open`

**NOTE**: before running the e2e tests the following env vars need to be set:

```dotenv
CYPRESS_AAD_TENANT_ID=
CYPRESS_AAD_CLIENT_ID=
CYPRESS_AAD_APP_CLIENT_SECRET=
CYPRESS_TEST_USER_EMAIL=
CYPRESS_TEST_USER_PASSWORD=
```

To generate GraphQL hooks
`npm run codegen`

## Development Setup with other @lca packages

You can use `npm link` to set up live reloading of the other `@lca` packages.

- Clone the package that you wish to enable live reload on.
- In the terminal, go the root folder of the cloned repo and write `npm link` in the terminal
- Go back to this repo's root folder and write `npm link @lca/{PACKAGE}` to link the package.
- When you make changes to the package, that you wish to see in this app, simply run `npm run build` in the package and
  the changes will available here.

## Folder Structure and Naming
```python
cypress/ # Contains E2E tests
    e2e/ # The tests themselves
    fixtures/ # Mock data
    support/ # Helper functions
src/ # Contains the source code
    app/ # Contains the App component
    assets/ # Contains assets, such as images
    components/ # React components
        myComponent/ # Each component has its own folder
            index.ts # Export of what is public
            myComponent.tsx # The component
            myComponent.spec.tsx # Unit test file
    dataAccess/ # Apollo Client folder
        generated.ts # Autogenerated file from Apollo with React Hooks for data fetching
        schema.graphql # File for writing GraphQL queries
    pages/ # Page components
    routes/ # Routing for the app
```

## Further Documentation

Further documentation for LCAcollect can be found [here](https://github.com/lcacollect/.github/blob/main/wiki/README.md)