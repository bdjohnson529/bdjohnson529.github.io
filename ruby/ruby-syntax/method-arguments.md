---
title: "Method Arguments"
layout: default
topic: ruby-syntax
order: 1
parent: Ruby
parent_path: /ruby/
---
With certain Ruby methods, you can pass arguments to the method by separating the argument from the function with a space.
```ruby
item = 'orange'
fruits = ['orange', 'grapefruit', 'apple']

x = fruits.include? item

puts x
```

This functionality breaks down when you are using more complicated statements, like ternary statements.
```ruby
item = 'orange'
fruits = ['orange', 'grapefruit', 'apple']

x = fruits.include? item ? 'You picked a fruit' : 'You did not pick a fruit'

puts x
```