---
title: "Ruby introduction"
layout: default
parent: Ruby on Rails
parent_path: /tutorials/ruby-on-rails
---
Rbenv is a tool for managing Ruby environments. A counterpart in Python might be *Anaconda*. To install *rbenv* on Ubuntu, use the following commands:
```bash
sudo apt update
sudo apt install rbenv
sudo apt install git curl libssl-dev libreadline-dev zlib1g-dev autoconf bison build-essential libyaml-dev libreadline-dev libncurses5-dev libffi-dev libgdbm-dev
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
source ~/.bashrc
```

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