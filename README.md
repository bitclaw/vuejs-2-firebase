# vuejs-2-firebase
VueJS 2 Firebase App

Firebase schema example:

```json
{
  "books":{
    "book1":{
        "author":"John",
        "title":"John Vincent",
        "url":"www.google.com"
    },
    "book2":{
        "author":"Wayne",
        "title":"Wayne's World",
        "url":"www.waynesworld.com"
    }
  }
 }
```

Initialize Vuejs2 project:

```shell
npm init
npm install vue-cli --save
vue init webpack vuejs-2-firebase
npm install
npm run dev
````

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# run unit tests
npm run unit

# run e2e tests
npm run e2e

# run all tests
npm test
```

For detailed explanation on how things work, checkout the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
