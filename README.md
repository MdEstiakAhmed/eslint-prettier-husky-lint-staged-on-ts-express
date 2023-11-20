# Boilerplate: typescript, express and mongodb

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
- install ts-node-dev: `npm install -D ts-node-dev`
- add or update start script in package.json: `"start": "ts-node-dev --respawn --transpile-only src/server.ts"`

## Step 4 (install packages)
- `npm install express`
- `npm install -D @types/express`
- `npm install mongoose`
- `npm install dotenv`


## if mongodb is not connected or connection error occurs:
run `sudo systemctl status mongod`
run `sudo systemctl start mongod`