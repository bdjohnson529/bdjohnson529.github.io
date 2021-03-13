---
title: "Webpacker"
layout: default
parent: Ruby on Rails
parent_path: /tutorials/ruby-on-rails
---
Webpacker is a gem which wraps `webpack`, a Javascript tool for compiling and bundling Javascript code. When Webpack is executed within a project, it constructs a dependency graph of the Javascript code and generates an output set of Javascript files. These JS files are transferred to the client web browser.

In Rails 6, Webpacker is the default Javascript compiler, replacing sprockets (another library for compiling and bundling Javascript). 

## Javascript in Rails 6
Rails 6 moved Javascript from the `app/assets` directory to `app/javascript/packs`. It is still possible to integrate JS files saved in `app/assets` but to avoid errors in the asset pipeline, it is best practice to save all JS to `app/javascript`.

Rails 6 also transitioned to a new helper method used to import Javascript into HTML views. Predecessors used [`javascript_include_tag`](https://apidock.com/rails/ActionView/Helpers/AssetTagHelper/javascript_include_tag) to create an HTML script tag for Javascript files. The new helper method, [`javascript_pack_tag`](https://www.rubydoc.info/github/rails/webpacker/Webpacker%2FHelper:javascript_pack_tag) is maintained by Webpacker. Hopefully this makes for an improved integration between Webpacker and Rails.

In the default configuration, Javascript packs are saved in `app/javascript/packs`. An `application.js` file can be used to import Javascript libraries which are necessary throughout the application. Javascript files specific to a page can be placed in separate files, within the `packs` folder. For example, the packs folder might look like this
```
├── app
|   ├── javascript
|       ├── packs
|           ├── application.js
|           ├── hello.js
```

To import `application.js` throughout the app, add the pack to `application.html.erb`:
```
<%= javascript_pack_tag 'application', 'data-turbolinks-track': 'reload' %>
```

## Webpacker Entry Point
The webpacker entry point is defined in `config/webpacker.yml`. One thing we've learned is having a singular entry point for the Javascript compiler makes it easier to troubleshoot the asset pipeline. Of course the default settings can be modified if absolutely necessary.
```
source_path: app/javascript
source_entry_path: packs
```

The Webpack API has a [ProvidePlugin](https://webpack.js.org/plugins/provide-plugin/) function which *automatically load modules instead of having to import or require them everywhere.* To integrate a third-party Javascript library into your app, simply use `ProvidePlugin` within `config/webpack/environment.js`. For example, to include JQuery,

```javascript
const { environment } = require("@rails/webpacker");

const webpack = require("webpack");
environment.plugins.prepend(
  "Provide",
  new webpack.ProvidePlugin({
    $: "jquery/src/jquery",
    jQuery: "jquery/src/jquery",
  })
);

module.exports = environment;
```





## Further reading
* [Disable cache on Chrome](https://www.technipages.com/google-chrome-how-to-completely-disable-cache)
* [Understanding webpacker in Rails 6](https://prathamesh.tech/2019/08/26/understanding-webpacker-in-rails-6/)
* [Using webpacker in your RoR app deep dive](https://blog.appsignal.com/2021/02/17/using-webpacker-in-your-ruby-on-rails-app-deep-dive.html)