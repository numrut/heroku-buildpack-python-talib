# Heroku Python TA-Lib package

This buildpack should be used in conjunction with the [official Heroku Python buildpack](https://github.com/heroku/heroku-buildpack-python).

```
~ $ heroku buildpacks:add --index 1 heroku/python
~ $ heroku buildpacks:add --index 2 numrut/ta-lib
```

## Using the latest buildpack code

The `numrut/ta-lib` buildpack from the [Heroku Buildpack Registry](https://devcenter.heroku.com/articles/buildpack-registry) contains the latest stable version of the buildpack. If you'd like to use the latest buildpack code from this Github repository, you can set your buildpack to the Github URL:

```
~ $ heroku buildpacks:add --index 2 https://github.com/numrut/heroku-buildpack-python-talib
```
