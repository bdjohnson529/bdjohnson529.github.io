---
title: "Methods"
layout: default
topic: ruby-syntax
order: 3
parent: Ruby
parent_path: /ruby/
---
Ruby methods are similar to functions in other programming languages. Method names need to start with a lower case letter so that the Ruby interpreter parses them correctly.

Methods are defined between an opening `def` statement and a closing `end` statement. Methods accept arguments, contained within parentheses. Methods also need to be defined, before they are invoked.
```ruby
def add_numbers(x, y)
    x + y
end

puts add_numbers(1,2)

>> 3
```

Ruby methods have an implicit return value, equal to the final method instruction. An explicit `return` statement can also be used to return one or more values. The Ruby parser will prioritize the explicit value over the implicit value.
```ruby
def reverse_numbers(x, y)
    return y, x
end

print reverse_numbers(1,2)

>> [1,2]
```