# Middleman Build Pack

This is a build pack for [Middleman](http://middlemanapp.com) that will
create your static site.

It is cleaner than most Middleman build packs out there because it
takes advantage of the [heroku-buildpack-multi](https://github.com/ddollar/heroku-buildpack-multi)
buildpack to separate out the Ruby and Middleman specific components.

It uses a simple HTTP server written in Go (see server.go) to server all static
pages and assets instead of standard `middleman server` command.

*derived from https://github.com/hashicorp/heroku-buildpack-middleman*

## Usage

This build pack is meant to be used with the
[heroku-buildpack-multi](https://github.com/ddollar/heroku-buildpack-multi)
buildpack. Setup generally goes like this with an existing Heroku app:

```
$ heroku config:add BUILDPACK_URL=https://github.com/ddollar/heroku-buildpack-multi.git
...
$ cat .buildpacks
https://github.com/heroku/heroku-buildpack-ruby.git
https://github.com/sosedoff/heroku-buildpack-middleman.git
```

Then just push!