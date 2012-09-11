# Heroku buildpack: Meteorite

This build pack allows you to easily deploy meteor apps to heroku using [meteorite](http://github.com/oortcloud/meteorite). It's easy to use different branches of meteor and any smart package you can lay your hands on.

_Coming soon_: Support for packages that rely on node modules, more goodies

## Usage

```
heroku create --stack cedar --buildpack https://github.com/oortcloud/heroku-buildpack-meteorite.git
```

Then `git push` to heroku as usual. 

_NOTE_: you need to have a verified account so the buildpack can add a `mongohq:free` addon.

## Usage with node 0.8

Meteor is mid transition to node 0.8, so if you are using a newer branch of meteor (e.g. `auth` or `devel`), you'll need to use a version of this buildpack that uses node 0.8.

You can change buildpack with:

```
heroku config:add BUILDPACK_URL=git://github.com/oortcloud/heroku-buildpack-meteorite.git#0.8
```

(or create with that same URL).
