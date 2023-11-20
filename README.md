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

## Step 4 (install packages)
- `npm install express`
- `npm install -D @types/express`
- `npm install dotenv`