This is a rebuilt keycloak-js library based on 10.0.2. 

It has one minor modification which you can see on this comparison https://github.com/datch-io/keycloak/compare/10.0.2...datch-io:feature%2Flogout-patch-ios?diff=split&expand=1.

This is to fix an issue discribed here: https://stackoverflow.com/questions/63993671/for-keycloak-angular-cordova-app-logout-only-seems-to-work-if-done-within-a/64908325#64908325

Build folder was originally: distribution/adapters/js-adapter-npm-zip

But this seems to pull its original files from somewhere else. So also built from here....

## Build steps

## Build steps

Go to `adapters/oidc/js` and run `mvn package` and copy the files from `adapters/oidc/js/target/classes` to `keycloak-js/dist` folder (this is so we can combine them with the package.json file and only deploy keycloak-js adapter).

Make your update to the package.json file in `keycloak-js` folder

Mavern version I was using: `Apache Maven 3.6.1 (d66c9c0b3152b2e69ee9bac180bb8fcc8e6af555; 2019-04-05T08:00:29+13:00)`

## Steps to publish to Datch npm registry
Go into the keycloak-js folder `./keycloak-js`.

You'll need the gcp artifact registry auth package.
`npm install -g google-artifactregistry-auth`

Authenticate with GCP artifact registry. This will use your gcp user login or service account credentials
`npx google-artifactregistry-auth`

Publish the package. any packages with the `@datch` scope will be published to the datch npm repo based on the config in `keycloak-js/.npmrc`
`npm publish`