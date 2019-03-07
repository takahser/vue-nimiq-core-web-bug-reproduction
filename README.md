# VUE.js / Nimiq Core Web Bug

## Expected behaviour

If running the vue app locally using `vue-cli-service serve` works, building the project using `vue-cli-service build` and running from a webserver should also work.

## Actual behaviour

- Running the vue app locally using `vue-cli-service serve` works.
- Building the project using `vue-cli-service build` and running from a webserver **doesn't work**. Instead, it fails with a console error:

```
Uncaught TypeError: Class extends value undefined is not a constructor or null
    at Module.<anonymous> (web.esm.js:1)
    at Module.6a96 (web.esm.js:1)
    at l (bootstrap:78)
    at Module.56d7 (HelloWorld.vue?91b6:20)
    at l (bootstrap:78)
    at Object.0 (bootstrap:151)
    at l (bootstrap:78)
    at r (bootstrap:45)
    at bootstrap:151
    at bootstrap:151
```

## Reproduction steps

```
# install dependencies
yarn install

# serving locally works
yarn serve

# building and serving from webserver fails
# i) create the build
# ii) run the built files in the /dist dir using the 'serve' web server package
yarn run serve:dist 
```
