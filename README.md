# Yarn Link TS React Example

This is an example of using a react component library (typescript) in another application in development (locally).
Typescript needs to be compiled with tsc in this example.

## Important Files
- tsconfig.json
  Make sure to set "jsx" with "react-jsx" if you are using react 17 and creating components without declaring "import React from 'react".
  
- package.json
  Make sure to point to the built folder locations with:
  ```
    "main": "./lib/cjs/index.js",
    "module": "./lib/esm/index.js",
    "types": "./lib/esm/index.d.ts",
    ...
  ```


## How to run the example application

### Component library (react)
    1. `yarn install` (first time only)
    2. `yarn link` (first time only)
    3. `yarn build`or `yarn build-watch` for hot-reload/watch mode.

### Host CRA App
    1. `yarn install` (first time only)
    2. `yarn link react-example-package` (first time only)
    3. `yarn start` to start the host application.

### Issue to watch out
The host app may complain 'Invalid hook call'.
In that case, refer this `https://stackoverflow.com/a/57422196/5089079`.

Basically,
1. you go to the host app -> node_modules -> go in to react folder. Then, run `yarn link`.
2. then, you cd into the component library root folder. Then, run `yarn link react`.  This will avoid duplicate reacts when developing locally.

    

