---
layout: post
title:      "What I discovered about Instance Methods."
date:       2020-04-19 19:27:56 +0000
permalink:  what_i_discovered_about_instance_methods
---


Between instance and class methods there is a short but very strong line. When I firstly interacted with a class/instance method I thought the difference will not be that important. After I saw the actual use of those methods I realised that the difference is huge in the matter of their usage.

Searching on Google I discovered one interesting aspect that might be interesting to know: 

### Under Ruby’s "hood", class methods don’t really exist.

Wait... What?!

```
class Train

  def self.metaclass
    class &lt;&lt; self; self; end
  end

  def self.depart
    # ...
  end
end

Train.metaclass.instance_methods.include? "depart" # =&gt; true
```

### They’re just instance methods on the class’s metaclass, which is an instance too, of Class.

In other words the only methods that really exists in Object Oriented Ruby are the instance methods.

