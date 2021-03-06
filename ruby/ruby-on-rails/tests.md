---
title: "Tests"
layout: default
topic: ruby-on-rails
order: 8
parent: Ruby
parent_path: /ruby/
---
Tests are used to validate our code and ensure it executes as expected. Rails has baked tests into the framework. When you create a model or controller, skeleton test files are generated in the directory `tests`. To execute application tests, run `bin/rails test`.

Test data is saved in the `test` database, which is defined in `config/database.yml`. Test data is defined using [`fixtures`](https://guides.rubyonrails.org/testing.html#the-low-down-on-fixtures) -- YAML files which are processed by the Rails engine. The rails engine can interpret ERB in the YAML files, a handy feature which allows us to write functions to populate the test database with lots of data.

# Model Tests
There are several ways we can test our models.
1. Attribute validation


## Attribute validation
[ActiveRecord validations](https://guides.rubyonrails.org/active_record_validations.html) can be used to validate model attributes, before creating an instance of the model. Validations prevent bad data from entering the database. Let's say you have a person model, with a height attribute. The height attribute is specified in inches, and must be a decimal number. Using an ActiveRecord validation, you could validate the `height` attribute.
```ruby
class Person < ApplicationRecord
  validates: :height, presence: true, numericality: { only_float: true, greater_than: 0 }
```

You could write a complementary test to capture this validation.
```ruby
# test/fixtures/users.yml
one:
    name: Joe Schmoe
    height: 173

# test/models/user_test.rb
class UserTest < ActiveSupport::TestCase
  def setup
    @user = users(:one)
  end

  test 'User is valid with valid attributes' do
    assert @user.valid?
  end

  test 'User is invalid with invalid height' do
    @user.height = 'string'
    refute @user.valid?, 'Saved user without a non-numeric height'
  end
```


## References
* [How To Test Rails Models with Minitest](https://semaphoreci.com/community/tutorials/how-to-test-rails-models-with-minitest)