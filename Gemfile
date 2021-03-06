# encoding: UTF-8
# -*- mode: ruby -*-
# vi: set ft=ruby :

source 'https://rubygems.org'

chef_version = ENV.key?('CHEF_VERSION') ? ENV['CHEF_VERSION'] : nil

group :doc do
  gem 'yard', '~> 0.8'
end

group :test do
  gem 'rake'
  gem 'berkshelf', '~> 4.0'
end

group :style do
  gem 'foodcritic', '~> 6.0'
  gem 'rubocop', '~> 0.41'
end

group :unit do
  gem 'chef', chef_version unless chef_version.nil? # Ruby 1.9.3 support
  gem 'simplecov', '~> 0.9'
  gem 'should_not', '~> 1.1'
  gem 'chefspec', '~> 4.2'
  gem 'rack', '~> 1.0' if RUBY_VERSION < '2.2.2'
end

group :integration do
  gem 'vagrant-wrapper', '~> 2.0'
  gem 'test-kitchen', '~> 1.2'
  gem 'kitchen-vagrant', '~> 0.15'
end

group :integration, :integration_cloud do
  gem 'kitchen-ec2', '~> 1.0'
  gem 'kitchen-digitalocean', '~> 0.8'
end

group :guard do
  gem 'guard', '~> 2.12'
  gem 'guard-foodcritic', '~> 2.0'
  gem 'guard-rubocop', '~> 1.2'
  gem 'guard-rspec', '~> 4.6'
  # Temporary disabled: Error is: cannot load such file -- guard/kitchen
  # gem 'guard-kitchen', '~> 0.0.0'
end

group :travis do
  gem 'coveralls', '~> 0.7', require: false
end
