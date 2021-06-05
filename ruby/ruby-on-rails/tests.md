---
title: "Tests"
layout: default
topic: ruby-on-rails
order: 8
parent: Ruby
parent_path: /ruby/
---
Tests are used to validate parts of our code (models, views or controllers) and ensure consistent code quality. Tests are saved in the directory `tests`. To run the tests, use `bin/rails test`.

## Model Tests
There are several ways we can test our models.
1. Model is valid with valid attributes
2. Model is invalid without a required attribute

Using fixtures, we can define the data for the data for the tests in a `yml` file. If we are testing a `user` model, we could use the fixture `test/fixtures/users.yml` to define the following:
```ruby
# test/fixtures/users.yml
one:
    name: Joe Schmoe
    email: joe@yahoo.com
```

This data can be accessed by the users test:
```ruby
require "test_helper"

class UserTest < ActiveSupport::TestCase
  def setup
    @user = users(:one)
  end

  test 'User is valid with valid attributes' do
    assert @user.valid?
  end

  test 'User is invalid without name' do
    @user.name = nil
    refute @user.valid?, 'Saved user without a name'
  end
```


## References
* [How To Test Rails Models with Minitest](https://semaphoreci.com/community/tutorials/how-to-test-rails-models-with-minitest)