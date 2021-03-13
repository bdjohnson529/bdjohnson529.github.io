---
title: "Ruby introduction"
layout: default
parent: Ruby on Rails
parent_path: /tutorials/ruby-on-rails
---
[RubyInstaller](https://rubyinstaller.org/) is a great way to install Ruby on Windows. Rbenv is a great Linux tool for managing Ruby environments.  A counterpart in Python might be *Anaconda*. Check out [this script](https://github.com/bdjohnson529/toolbox_linux/blob/master/wsl2_ubuntu_1804/install_ruby.sh) to install *rbenv* on Ubuntu.

Using Rbenv, we can install a specific version of Ruby:
```bash
rbenv install -v 2.6.6
rbenv global 2.6.6
```

## Ruby Gems
Gem is the package manager for Ruby. Each language has one or more package managers - Python uses *pip*, and Javascript uses *npm*. Ruby packages are called *gems*. To install the rubocop gem, for example, you can type the following into the command line.
```bash
gem install rubocop
```

Verify installation
```bash
which rubocop
```

## Bundler
*Bundler provides a consistent environment for Ruby projects by tracking and installing the exact gems and versions that are needed.* **- [Bundler.io](https://bundler.io/)**

Using Bundler you can install a list of Ruby gems from a *Gemfile*. Bundler tries to make sure that you have the proper version of all dependencies. Using bundler is *usually* as simple as

```bash
bundle install
```


## Yarn
Yarn is a package manager for NodeJS. To install and upgrade node modules,
```bash
yarn install
yarn upgrade
```