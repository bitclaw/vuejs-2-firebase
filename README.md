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
npm install firebase vuefire --save
npm install jquery --save
npm install bootstrap-sass --save
npm install sass-loader --save
npm install node-sass --save
npm run dev
````

Add the following code to build/webpack.base.conf.js

```json
 {
   test: /\.scss$/,
   loaders: [ 'style-loader', 'css-loader', 'sass-loader' ]
 },
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

## Useful links

https://www.airpair.com/firebase/posts/structuring-your-firebase-data
https://vuejs.org/v2/examples/firebase.html
https://scotch.io/tutorials/building-a-google-keep-clone-with-vue-and-firebase-pt-1
https://scotch.io/tutorials/building-a-google-keep-clone-with-vue-and-firebase-pt-2
https://coligo.io/bookmarking-app-electron-vuejs-firebase/
https://www.udemy.com/vuejs-2-the-complete-guide/?siteID=a1o1REVAqJg-exWOTV0WFdxs3NCRugXmwQ&LSNPUBID=a1o1REVAqJg
