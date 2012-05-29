# Heroku buildpack: Meteor, npm compatible

This is a fork of the [Node.js buildpack](https://github.com/heroku/heroku-buildpack-nodejs), and I've left it nearly intact apart from manually combining the bin/* files from [Jordan Sissel's meteor buildpack](https://github.com/jordansissel/heroku-buildpack-meteor).

This combination buildpack allows us to setup our Meteor project as an npm package (via package.json, as recommended by Heroku for Node.js installations on the cedar stack).

## Usage

```
heroku create --stack cedar --buildpack https://github.com/matb33/heroku-buildpack-nodejs.git
```

If you get a `! Resource not found` message like I did, then split up the create into two steps (though make sure to `heroku apps:destroy` your previous attempt):

```
heroku create --stack cedar
heroku config:add BUILDPACK_URL=https://github.com/matb33/heroku-buildpack-nodejs.git
```

## Example

See [this project](https://github.com/matb33/heroku-meteor-npm) for an example that leverages this frankenstein buildpack.