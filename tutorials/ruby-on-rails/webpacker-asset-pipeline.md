---
title: "Webpacker asset pipeline"
layout: default
parent: Ruby on Rails
parent_path: /tutorials/ruby-on-rails
---
Webpacker is a gem which wraps `webpack`, a Javascript tool for compiling and bundling Javascript code. 

# Application entry points
The entry point is the file which webpacker looks for first when compiling Javascript. The application entry points are defined in `app/javascript/packs`. On installation, the webpacker gem automatically creates an `application` pack, which is defined in `app/javascript/packs/application.js`.

Webpacker compiles javascript into *packs*. To include these packs in your application, use a helper method `javascript_pack_tag`. For example, to include the `application` pack in all views, add the following line to `layouts/application.html.erb`:
```
<%= javascript_pack_tag 'application' %>
```

The entry point is defined in `config/webpacker.yml`:
```
source_entry_path: packs
```





## Further reading
* [Disable cache on Chrome](https://www.technipages.com/google-chrome-how-to-completely-disable-cache)
* [Understanding webpacker in Rails 6](https://prathamesh.tech/2019/08/26/understanding-webpacker-in-rails-6/)
* [Using webpacker in your RoR app deep dive](https://blog.appsignal.com/2021/02/17/using-webpacker-in-your-ruby-on-rails-app-deep-dive.html)