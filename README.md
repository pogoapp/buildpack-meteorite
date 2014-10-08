# Heroku buildpack: Meteor v0.9

This build pack allows you to easily deploy meteor apps to heroku using [meteorite](http://github.com/oortcloud/meteorite). It's easy to use different branches of meteor and any smart package you can lay your hands on.

## Usage

```bash
heroku create --stack cedar --buildpack https://github.com/oortcloud/heroku-buildpack-meteorite.git
```

Then `git push` to heroku as usual.

## NOTES

You need to set the `ROOT_URL` environment variable:

```bash
heroku config:add ROOT_URL=your.domain.com
```

And it also seems that you have to set either or both `MONGO_URL` or `MONGODB_URL` environment variable.
It seems that mongohq has changed the Variable name to `MONGOHQ_URL`:

```bash
heroku config:add MONGO_URL=mongodb:patch.to.mongo
heroku config:add MONGODB_URL=mongodb:patch.to.mongo
```
> I need to figure out if maybe I can adjust the script to take the newly variable

You can specify meteor settings by setting the `METEOR_SETTINGS` environment variable:

```bash
heroku config:add METEOR_SETTINGS='{"herp":"derp"}'
```


You need to have a verified account so the buildpack can add a `mongohq:sandbox` addon.
