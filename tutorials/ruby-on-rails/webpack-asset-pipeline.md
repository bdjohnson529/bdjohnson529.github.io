---
title: "Webpack asset pipeline"
layout: default
parent: Ruby on Rails
parent_path: /tutorials/ruby-on-rails
---
The entry point for assets is the HTML file which is rendered by the client's browser. In Rails, the HTML file served at a specific route is generated as a combination of the `html.erb` files in `app/views/`.

Assets are imported in views. The `layouts/application.html.erb` defines assets which are included in all views. In this tutorial we demonstrate how to include two types of assets: javascript and scss. First, add the following lines to `application.html.erb`, in the `<head>` element:
```
<%= stylesheet_link_tag 'application', media: 'all'%>
<%= javascript_pack_tag 'application' %>
```

The [first element](https://api.rubyonrails.org/classes/ActionView/Helpers/AssetTagHelper.html#method-i-stylesheet_link_tag) is an instance of `ActionView::Helpers::ActionClassHelper`. The `ActionView` will generate the HTML element below. Notice how the second set of arguments passed to the `ActionView` becomes attributes of the HTML element.
```html
<link href="assets/application.css" media="all">
```

## SCSS Files
To define a site-wide font styling in a CSS file, create a `_layout.scss` file which defines CSS properties such as color, font-size, and text alignment. 

`app/assets/stylesheets/_layout.scss`
```css
h1 {
    font-family: 'Montserrat';
    font-size: 32px;
    text-align: center;
}
```
And import this into the SCSS entry point,

`app/assets/stylesheets/application.scss`:
```css
@import "_layout";
```
Finally, import `application.scss` into the `html.erb` file which is added to each HTML page.

`app/views/layouts/application.html.erb`.
```
<head>
  <%= stylesheet_link_tag 'application' %>
</head>
```

## Javascript
Webpack can be used to import javascript files. Make sure you [disable your cache](https://www.technipages.com/google-chrome-how-to-completely-disable-cache) as it is hard to develop otherwise.