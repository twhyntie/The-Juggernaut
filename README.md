Juggernaut
================

[![Build Status](https://travis-ci.org/zooniverse/The-Juggernaut.png)](https://travis-ci.org/zooniverse/The-Juggernaut)

# Getting Started

To run this application we recommend MySQL and Ruby > 1.8.6 (1.8.7, 1.9.2-p290). Please note the application has not been tested against versions of Ruby later than 1.9.2-p290. This guide assumes that you have RVM installed to manage your Rubies.

## RVM & Rubygems

You'll need to have RVM installed from here on out. If you don't have it you can find install instructions [here](https://rvm.io/).

If you don't already have it then go ahead and grab Ruby 1.9.2:

```bash
rvm install ruby-1.9.2-p290
```

Then switch to that Ruby and create a new gemset for this application:

```bash
rvm 1.9.2-p290@juggernaut --create #note the --create makes a new gemset if you don't already have one.
```

Next you need to grab the gems for the application. Assuming you're in The-Juggernaut checked out repo locally you can do this as follows:

```bash
bundle
```

## Configuring the database

Next we need to set up the database for the application. The configuration is in config/database.yml  and by default is set up as follows:

```yaml
development:
  adapter: mysql2
  host: localhost
  username: root
  password: 
  database: the_juggernaut_development
```

Modify these settings for your particular setup (username/password) and when you're ready to create your databases and set up the database structure run the following:

```ruby
rake db:create
rake db:schema:load
```

## Booting the application

Provided all of the previous steps have run without error you should now be able to boot the application screen by executing the standard Rails boot:

```ruby
rails server
```

Checking in on [http://0.0.0.0:3000](http://0.0.0.0:3000) you should see a page render with the message 'You need to log in · Would you like to classify some images?'

