---
title: "Add ajax to ruby on rails 6"
layout: default
parent: Ruby on Rails
parent_path: /tutorials/ruby-on-rails
---
# Add ajax to ruby on rails 6

Modify `config/webpack/environment.js`, and add the following lines:
```javascript
environment.plugins.prepend('Provide',
  new webpack.ProvidePlugin({
    $: 'jquery/src/jquery',
    jQuery: 'jquery/src/jquery'
  })
)
```

Add the following line to `assets/javascripts/application.js`:
```javascript
//= require jquery
```




## Resources
* [Introducing jQuery in Rails 6 Using Webpacker](https://www.botreetechnologies.com/blog/introducing-jquery-in-rails-6-using-webpacker/)