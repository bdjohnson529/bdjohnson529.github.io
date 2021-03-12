---
title: "SCSS Assets"
layout: default
parent: Ruby on Rails
parent_path: /tutorials/ruby-on-rails
---
*Previous Rails versions placed all assets in sudirectories of `public`. Any assets under public will be served as static files by the application or web server when config.public_file_server.enabled is set to true.*
*  [**Ruby on Rails asset pipeline**](https://guides.rubyonrails.org/asset_pipeline.html#how-to-use-the-asset-pipeline)

Assets can be placed in one of two places, `public`, or `app/assets`. Assets in the `public` folder are served as is, while assets in the `app/assets` folder are precompiled. Most assets we write are going to be precompiled; for example, SCSS files are compiled into CSS.

# SCSS Files
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