# heroku-buildpack-sweettooth-storefront-js

**heroku-buildpack-sweettooth-storefront-js** enables you to run your ES6 application on Heroku with the help of Gulp.

# What Is It!?

This buildpack allows you to push - without building - to Heroku, that way it is trans-/compiled on Heroku, thus eliminating
room for error in terms of versioning, architecture, etc.

There are 3 folders:

```
.
├── bin
│   ├── compile
│   ├── detect
│   ├── release
├── scripts
│   ├── static.json
└── vendor
    └── jq       
```

* `bin` is responsible for most of the work
  * The `detect` script is used to make a check that makes sure we're running with a correct application, in our case, we're checking
  that we pushed a Node.js project
  * The `release` script is one that needs to be there, but can be used for versioning; not in use right now
  * The `compile` script is used to run the compilation; it is manually setting up the environment to run and host our application
* `scripts` hosts external files that we will need to used
* `vendor` hosts third-party scripts (or services) that we are using
  * `jq` is a JSON parser used to grab keys from `package.json` such as Node engine and `npm start` 
