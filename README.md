# Omeka::Recipes

Useful Capistrano recipes including:

* Create MySQL database and user on server (via prompts)
* Restart/Stop/Start Apache/HTTPD server
* Log rotation and tailing commands
* Deploy Omeka

## Included Tasks

* `cap apache:stop`
* `cap apache:start`
* `cap apache:restart`
* `cap apache:reload`
* `cap db:create_ini`
* `cap db:mysql:setup`
* `cap db:myql:dump`
* `cap db:myql:fetch_dump`
* `cap db:myql:restore`
* `cap log:rotate`
* `cap log:tail`
* `cap omeka:symlinks`
* `cap omeka:themes`
* `cap omeka:plugins`

## Installation

Add this line to your application's Gemfile:

    gem 'omeka-recipes'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install omeka-recipes
 
## Usage

To set up the initial Capistrano deploy file, go to your application
folder in the command line and enter the `capify` command:

    $ capify .

### Configuration

Inside a newly created `config/deploy.rb` file, add this:

```ruby
require 'capistrano/ext/multistage'

# This should go at the end of the deploy.rb file
require 'capistrano_omeka'
```

### RVM

RVM is enabled by default, but you can disable it by setting `:use_rvm,
false`. You may also leverage it by setting your `rvm_ruby_string` to an
appropriate version (default is `1.9.3`).

If `using_rvm` is true, the rvm recipe will load the RVM capistrano
extensions so you don't have to worry about them during your
deployments. You will need to make sure you have an `.rvmrc` file in the
project directory, and system-wide installation on the servers.

See [http://rvm.beginrescueend.com/rvm/install](the rvm site) for more information.

# Copyright

See the [LICENSE] for more information.

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
