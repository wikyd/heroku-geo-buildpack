Fork
=====================
Remove dependency on gdal.

Heroku buildpack: geo
=====================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) that
vendors main geo/gis libraries like geos, proj.

It is meant to be used in conjunction with other buildpacks as part of a
[multi-buildpack](https://github.com/ddollar/heroku-buildpack-multi).

Usage
-----

Example usage:

    $ heroku config:add BUILDPACK_URL=https://github.com/ddollar/heroku-buildpack-multi.git

    $ cat .buildpacks
    https://github.com/wikyd/heroku-geo-buildpack.git#1.4
    https://github.com/heroku/heroku-buildpack-ruby.git#v129


Don't forget to pin buildpack versions you want to use in your .buildpacks file.

Testing
-------

For rgeo:

```ruby 
>>> require 'rgeo'
>>> RGeo::CoordSys::Proj4.supported?
=> true
>>> RGeo::Geos.supported?
=> true
```
