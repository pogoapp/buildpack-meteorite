# Heroku buildpack: Meteorite

This build pack allows you to easily deploy meteor apps to heroku using [meteorite](http://github.com/oortcloud/meteorite). It's easy to use different branches of meteor and any smart package you can lay your hands on.

_Coming soon_: Support for packages that rely on node modules, more goodies

## Usage

```
heroku create --stack cedar --buildpack https://github.com/oortcloud/heroku-buildpack-meteorite.git
```

Then `git push` to heroku as usual. 

_NOTE_: you need to have a verified account so the buildpack can add a `mongohq:sandbox` addon.
