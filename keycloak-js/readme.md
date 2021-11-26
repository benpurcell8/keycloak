This is a rebuilt keycloak-js library based on 10.0.2. 

It has one minor modification which you can see on this comparison https://github.com/datch-io/keycloak/compare/10.0.2...datch-io:feature%2Flogout-patch-ios?diff=split&expand=1.

This is to fix an issue discribed here: https://stackoverflow.com/questions/63993671/for-keycloak-angular-cordova-app-logout-only-seems-to-work-if-done-within-a/64908325#64908325

Build folder was originally: distribution/adapters/js-adapter-npm-zip

But this seems to pull its original files from somewhere else. So also built from here....

## Build steps

Go to `distribution/adapters/js-adapter-npm-zip` and run `mvn package` and copy the files across from `distribution/adapters/js-adapter-npm-zip/target/keycloak-js-adapter-npm-dist-10.0.2.zip` to the keycloak-js/dist folder (this is so we can combine them with the package.json file and only deploy keycloak-js adapter).

Mavern version I was using: `Apache Maven 3.6.1 (d66c9c0b3152b2e69ee9bac180bb8fcc8e6af555; 2019-04-05T08:00:29+13:00)`

## Steps to publish

Go into the keycloak-js folder. On your command line run `npm publish -registry https://registry.datch.io`