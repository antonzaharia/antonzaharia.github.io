---
layout: post
title:      "Classes and Instances"
date:       2020-04-02 15:01:00 +0000
permalink:  classes_and_instances
---


When I firstly faced these ideas of classes and instances I was thinking that they are kind of complex methods. Then I start understanding that classes are actually kind of a matrix that create "real" objects.
Let's assume the following class.
```
class Person
  attr_accessor :name
    def initialize(name)
    @name = name
  end
end
```
(Simpler than that I couldn't imagine) This `Person` class is actually creating new instances with different attributes just by calling `Person.new(name)`. This is the first time I meet this concept in coding and I thing it's amazing.

