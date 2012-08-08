source 'http://rubygems.org'

if File.exist? 'Gemfile.local'
  instance_eval(Bundler.read_file('Gemfile.local'), 'Gemfile.local', 1)
end

RAILS_VERSION = '= 3.2.6'
# XXX 3.2.6

# Get latest psych - work around crash during reorg migration
# gem 'psych'

#gem 'gdata-ruby-util', '1.1.2'
gem 'gdata_19',
  :git => 'https://github.com/tokumine/GData.git',
  :ref => '14e5a8a1381f4d50bc99ed083d89101f5111e3ea',
  :require => 'gdata'

platforms :ruby do
  group :development, :test do
    gem 'sqlite3'
  end

  group :heroku do
    gem "pg"
  end

  group :staging do
    gem "mysql"
  end

  group :production do
    gem "mysql"
  end
end

platforms :jruby do
  #gem 'jdbc-sqlite3', :require => false
  gem 'activerecord-jdbcsqlite3-adapter'
  gem 'jdbc-mysql', :require => false
  gem 'jruby-openssl'
  gem 'therubyrhino'
end

gem 'authlogic'
#gem 'dalli'
gem 'builder'
gem 'json'

gem 'acl9'

gem 'rails', RAILS_VERSION

gem 'haml', :git => 'https://github.com/haml/haml.git', :ref => '3-2-stable'
gem 'sass'
gem 'haml-rails'

# Used to be pulled in by dm-types
gem 'bcrypt-ruby'

gem 'prawn' # PDF generation

gem 'paper_trail', '~> 2'

gem 'awesome_nested_set'

group(:development, :test) do

  # Uncomment this if you want to use rspec for testing your application

  gem 'rspec-rails'
  gem 'spork', '~> 0.9.0.rc'
  gem 'ZenTest'
  gem 'autotest-rails'
  gem 'simplecov', :require => false

  gem 'factory_girl_rails', "~> 4.0"

  # To get a detailed overview about what queries get issued and how long they take
  # have a look at rails_metrics. Once you bundled it, you can run
  #
  #   rails g rails_metrics Metric
  #   rake db:automigrate
  #
  # to generate a model that stores the metrics. You can access them by visiting
  #
  #   /rails_metrics
  #
  # in your rails application.

  # gem 'rails_metrics', '~> 0.1', :git => 'git://github.com/engineyard/rails_metrics'

  platform :jruby do
    gem 'ruby-debug'
  end
  platform :ruby do
    gem 'linecache19', :git => 'git://github.com/mark-moseley/linecache'
    gem 'ruby-debug-base19x', '~> 0.11.30.pre4'
    gem 'ruby-debug19', :require => 'ruby-debug'
    gem 'ruby-prof'
  end

  # Causes rake to fail, uncomment to rebuild docs
  #gem 'yard-dm'
  # XXX gem 'yard'
  # XXX gem 'redcarpet'
  gem 'test-unit'
end

