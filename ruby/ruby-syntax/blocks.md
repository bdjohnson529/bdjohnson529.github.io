---
title: "Blocks"
layout: default
topic: ruby-syntax
order: 2
parent: Ruby
parent_path: /ruby/
---
Blocks are, well, *blocks* of code which can be passed into methods. A block can be enclosed by `do..end` or by brackets `{..}`. Blocks are often passed to iterators, to perform the same function on members of an array. Consider this code:
```ruby
[1,2,3].each do |x|
    puts x + 2
end

>> 3
>> 4
>> 5
``` 

The same code can be written by enclosing the block in brackets.
```ruby
[1,2,3].each do |x| { puts x + 2}
```

Blocks can be passed to methods. The block of code is evaluated within the method.

```ruby
def say_hello
    yield
end

say_hello { puts "Hello" }

>> Hello
```