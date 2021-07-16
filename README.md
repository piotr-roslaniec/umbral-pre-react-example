
# notes:
the dependencies for this include:
```
"umbral-pre": "file:./../rust-umbral/umbral-pre-wasm/pkg/",...
"nucypher-ts": "file:./../nucypher-ts",
```
for best results,

*  have these repos checked out in the same location as this repo
    * like:
        * /rust-umbral
        * /nucypher-ts
        * /this-repo

some install hacks...
```
before install:

# build umbral-pre-wasm
    cd ../rust-umbral/umbral-pre-wasm/
    make -B
    cd -

# next we need to modify the build script in nucypher-ts so it only builds itself and doesn't worry about umbral

    in ../nucypher-ts/package.json
    change
        "build": "yarn build:umbral:bundler && tsdx build",
    to
        "build": "tsdx build",

# then we can install this react app
yarn install
yarn start
```
then you should see something in your browser that looks like what is here: http://nucypher-web-tests.s3-website-us-west-1.amazonaws.com/

## nucypher-ts
nucypher-ts installs fine, but does not work and is commented out.  We need to figure out how to import it or maybe tweak it so it can support an injectable umbral module.



## Available Scripts ( from create-react-app)

In the project directory, you can run:

### `yarn start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.\
You will also see any lint errors in the console.

### `yarn test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `yarn build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.
