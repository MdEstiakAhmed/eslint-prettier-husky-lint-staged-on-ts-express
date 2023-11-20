# A boilerplate for typescript-express project with eslint, prettier, husky and lint-staged

# Create boilerplate from scratch
## Step 1 (initialize npm): 
- `npm init -y` (update package.json according to your description)
- Update entry point in package.json to `src/server.ts`
- Create `src` folder and `server.ts` file inside it

## Step 2 (install and setup typescript):
- install typescript: `npm install -D typescript`
- create tsconfig.json: `npx tsc --init`
- update tsconfig.json
    ```
    "target": "es6"
    "module": "commonjs"
    "outDir": "./dist"
    "rootDir": "./src"
    ```
- add include and exclude at root level in tsconfig.json
    ```
    "include": ["src/**/*"]
    "exclude": ["node_modules"]
    ```
- install ts-node-dev: `npm install -D ts-node-dev`
- add or update start script in package.json: `"start": "ts-node-dev --respawn --transpile-only src/server.ts"`

## step 3 (install eslint and prettier):
- `npm install -D eslint @typescript-eslint/parser @typescript-eslint/eslint-plugin`
- create eslint config file: `npx eslint --init`
- install prettier: `npm install -D prettier eslint-config-prettier`

## Step 4 (install husky and lint-staged)
- install husky: `npx husky-init && npm install`
- install lint-staged: `npm install -D lint-staged`
- update package.json
    ```
    "lint-staged": {
        "src/**/*.{js,ts,json,css,scss,md}": [
            "eslint --fix",
            "prettier --write"
        ]
    }
    ```
- update husky pre-commit in `*/.husky/pre-commit`
    ```
    npx lint-staged
    ```

## Step 5 (install packages)
- `npm install express`
- `npm install -D @types/express`
- `npm install dotenv`

## script commands:
- `npm start`: start the server
- `npm run lint:check"`: check lint the code
- `npm run lint:fix`: fix lint errors
- `npm run lint:staged`: lint staged files (only used by lint-staged)
- `prettier:check`: check prettier errors
- `prettier:fix`: fix prettier errors
- `prettier:staged`: prettier staged files (only used by lint-staged)
- `lint-prettier:check`: check lint and prettier errors
- `lint-prettier:fix`: fix lint and prettier errors
- `prepare`: husky prepare command (only used by husky)

*** update lint-staged in package.json
```
  "lint-staged": {
    "src/**/*.{js,ts,json,css,scss,md}": [
      "npm run lint:staged",
      "npm run prettier:staged"
    ]
  }
```