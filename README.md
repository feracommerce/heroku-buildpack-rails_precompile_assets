# Rails Precompile Assets Buildpack
For test environments this buildpack will compile assets for each environment.

# Why is this useful?
Heroku by default will not precompile assets in your build process if it finds a Manefest file in your repo. That makes sense, right?

However, what if you want to run a test server that tests your latest master branch? Well your options are:
1. Ensure that every time you modify an asset in your repo you also run `rake assets:precompile`. This sucks because if you modify an asset twice before deploying, you'll now have 2 different compiled assets in your repo (and running `assets:clean` too often is not a good idea since it breaks some old asset caches).
2. *The Better Option*: Use this buildpack only in your Test server dynos and it will precompile assets for you automatically.

