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

# Third Step

This last step consists in adding the TailwindCSS dependency, and the configuration so it can be included in the application layout.

## Add TailwindCSS

  yarn add tailwindcss

This adds the depency in package.json and yarn.lock

## Configure files

Adds file app/javascript/stylesheets/application.scss, with the content:

```
@import "tailwindcss/base";
@import "tailwindcss/components";
@import "tailwindcss/utilities";
```

And adds the reference to the new file in app/javascript/packs/application.js

  require("stylesheets/application.scss")

Adds in the postcss.config.js file the tailwindcss plugins:

```
require('tailwindcss'),
require('autoprefixer'),
```

You shoule be able to execute bin/webpack, and see that the file application.scss is compiled

## Add application.scss to layout

In order to view the new TailwindCSS style, should included it in the layout/application, as:

```
<%= stylesheet_pack_tag 'application', media: 'all', 'data-turbolinks-track': 'reload' %>
```

