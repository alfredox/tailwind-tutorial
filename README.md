# README

This project is a tutorial for integrating TailwindCSS framework into 
Rails.

Using:

* Ruby 2.7.1
* Rails 6.0.3

# First step

* Create the rails app, with the command:

  rails new tailwind-tutorial --webpack=stimulus
  
# Second Step

* Add a default action: home/index:

  rails g controller home index
  
* Add in the config/routes.rb the default root:

  root to: 'home#index'


