#step-by-step

- go to github.com

  - create new repo 'app-example'
  - repo_url: 'https://github.com/user/app-example.git'

- go to dev folder

  - `mkdir app`
  - `cd app && yarn init`
  - `code .`

- setup dev configs

  - `mkdir .vscode && touch .vscode/settings.json`
  - add content to settings.json

  - `touch .editorconfig`
  - add content to .editorconfig

  - `touch .prettierrc`
  - add content to .prettierrc

  - `touch .eslintignore`
  - add content to .eslintignore

  - `touch .env`
  - add content to .env

- setup git configs

  - `touch .gitignore`
  - add content to .gitignore
  - `touch README.md`
  - `touch LICENSE.md`
  - `git init`
  - `git add .`
  - `git commit -m 'initial commit'`

  - `git remote add origin repo_url`
  - `git push -u origin master`

- install dependencies

  - `yarn add express`
  - `yarn add cors`
  - `yarn add -D typescript`
  - `yarn add -D ts-node-dev`
  - `yarn add -D eslint prettier eslint-config-prettier eslint-plugin-prettier`

- initialize TS compiler

  - `yarn tsc --init`
  - configure tsconfig.json

    - lib?
    - skipLibCheck? true?

    - outDir: ./dist
    - rootDir: ./src

    - noImplicitAny: false ??
    - noEmit: false
    - target: es5 | es6
    - allowJs: true
    - forceConsistentCasingInFileNames: true
    - moduleResolution: node

    - module? commonjs exnext ...
    - isolatedModules?
    - resolveJsonModule?
    - strict?
    - esModuleInterop?
    - allowSyntheticDefaultImports?

- setup node scripts

  - "dev": "ts-node-dev --transpile-only --ignore-watch node_modules --respawn src/server.ts",
  - "build": "tsc -p .",
  - "start": "node dist/server.js"

- initialize ESLint

  - `yarn eslint --init`
  - configure .eslintrc.json

    - env: {
      es2020: true
      node: true
      }
    - parser: "@typescript-eslint/parser"
    - parserOptions: {
      "ecmaVersion": 11
      }
    - plugins: [
      "@typescript-eslint",
      "prettier"
      ]
    - extends: { (check this)
      "google|airbnb|standard",
      "plugin:@typescript-eslint/recommended",
      "prettier/@typescript-eslint",
      "plugin:prettier/recommended"
      }
    - rules: {
      "prettier/prettier": "error"
      }

- create root directory

  - `mkdir src`

- create out directory

  - `mkdir dist`

- imlement basic express server

  - `touch src/server.ts && code src/server.ts`
  - `touch src/app.ts && code src/app.ts`

- develop

  - `yarn dev` (tsnd src/server.ts)

- compile

  - `yarn build` (tsc -p .)

- run

  - `yarn start` (node dist/server.js)
