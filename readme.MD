### Ruby Sinatra Puma on Heroku

Skeleton of Puma Ruby run on Heroku.

#### Local

run `puma`

```
[3638] Puma starting in cluster mode...
[3638] * Version 3.11.4 (ruby 2.2.4-p230), codename: Love Song
[3638] * Min threads: 5, max threads: 5
[3638] * Environment: development
[3638] * Process workers: 2
[3638] * Preloading application
[3638] * Listening on tcp://0.0.0.0:5000
[3638] Use Ctrl-C to stop
[3638] - Worker 0 (pid: 3642) booted, phase: 0
[3638] - Worker 1 (pid: 3649) booted, phase: 0
```

### Production

1. Install [heroku-cli](https://devcenter.heroku.com/articles/heroku-cli)
2. Do `heroku login`
3. Do `heroku create` and let heroku create the app.
   ```
   Creating app... done, ⬢ radiant-earth-77144
   https://radiant-earth-77144.herokuapp.com/ | https://git.heroku.com/radiant-earth-77144.git
   ```
4. Push the the code `git push heroku master` into Heroku repo and let Heroku deploy the app in live.
  ```
  Counting objects: 10, done.
  Delta compression using up to 8 threads.
  Compressing objects: 100% (7/7), done.
  Writing objects: 100% (10/10), 1.09 KiB | 1.09 MiB/s, done.
  Total 10 (delta 0), reused 0 (delta 0)
  remote: Compressing source files... done.
  remote: Building source:
  remote:
  remote: -----> Ruby app detected
  remote: -----> Compiling Ruby/Rack
  remote: -----> Using Ruby version: ruby-2.3.7
  remote: -----> Installing dependencies using bundler 1.15.2
  remote:        Running: bundle install --without development:test --path vendor/bundle --binstubs vendor/bundle/bin -j4 --deployment
  remote:        Warning: the running version of Bundler (1.15.2) is older than the version that created the lockfile (1.16.1). We suggest you upgrade to the latest version of Bundler by running `gem install bundler`.
  remote:        Fetching gem metadata from https://rubygems.org/.........
  remote:        Fetching version metadata from https://rubygems.org/.
  remote:        Using bundler 1.15.2
  remote:        Fetching mustermann 1.0.2
  remote:        Fetching puma 3.11.4
  remote:        Fetching rack 2.0.5
  remote:        Installing mustermann 1.0.2
  remote:        Installing puma 3.11.4 with native extensions
  remote:        Installing rack 2.0.5
  remote:        Fetching tilt 2.0.8
  remote:        Installing tilt 2.0.8
  remote:        Fetching rack-protection 2.0.1
  remote:        Installing rack-protection 2.0.1
  remote:        Fetching sinatra 2.0.1
  remote:        Installing sinatra 2.0.1
  remote:        Bundle complete! 2 Gemfile dependencies, 7 gems now installed.
  remote:        Gems in the groups development and test were not installed.
  remote:        Bundled gems are installed into ./vendor/bundle.
  remote:        Bundle completed (3.91s)
  remote:        Cleaning up the bundler cache.
  remote: -----> Writing config/database.yml to read from DATABASE_URL
  remote: -----> Detecting rake tasks
  remote:
  remote: ###### WARNING:
  remote:        You have not declared a Ruby version in your Gemfile.
  remote:        To set your Ruby version add this line to your Gemfile:
  remote:        ruby '2.3.7'
  remote:        # See https://devcenter.heroku.com/articles/ruby-versions for more information.
  remote:
  remote: -----> Discovering process types
  remote:        Procfile declares types     -> web
  remote:        Default types for buildpack -> console, rake
  remote:
  remote: -----> Compressing...
  remote:        Done: 18.1M
  remote: -----> Launching...
  remote:        Released v4
  remote:        https://radiant-earth-77144.herokuapp.com/ deployed to Heroku
  remote:
  remote: Verifying deploy... done.
  To https://git.heroku.com/radiant-earth-77144.git
   * [new branch]      master -> master
  ```
5. Sinatra app will live on heroku e.g https://radiant-earth-77144.herokuapp.com

### ENV configurations.

#### WEB_CONCURRENCY

Number of workers. Defaut is 2. Read [workers](https://devcenter.heroku.com/articles/deploying-rails-applications-with-the-puma-web-server#workers) for more info.

#### MAX_THREADS

Number of threads. Default is 5. Read [threads](https://devcenter.heroku.com/articles/deploying-rails-applications-with-the-puma-web-server#threads) for more info.

#### PORT

Rack port. Default is 5000.
#### RACK_ENV

Rack environment. Default is development.
