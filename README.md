

### Classes and Instances

<img src="https://after-school-assets.s3.amazonaws.com/coffee.gif" width="300px" align="right" hspace="10">A class is a 'blueprint' or 'template' for making standardized versions of items. Any object in the real world can be modeled as an object in code. For example, here's a model for a coffee cup:

```ruby
class CoffeeCup

end
```
To create an individual version (known as an **instance** or **object**) of our class, we use the `.new` method on the class to create the instance:
```ruby
first_cup = CoffeeCup.new
```
### Attributes

All objects have characteristics that make them unique. For example, a coffee cup has a width, a height, a color, etc. We can add characteristics (known as **attributes**) to our model by using **writer and reader methods**. A writer method is like a statement telling your object “You are this tall” or “Your color is blue.” A reader is more like a response to a question asking the instance: “How tall are you?” or “What is your color?” The reader replies, "I am 6 feet tall" or "I am blue." A reader is a method that describes the attribute, while a writer method uses the `=` with an argument to set or change the attribute.

Here is a writer that takes in a color as an argument and sets it to the `@color` variable:
```ruby
def color=(color)
  @color = color
end
```

Here is a reader that returns the `@color` variable:
```ruby
def color
  @color
end
```

Note: We use `@variables`, known as **instance variables**, because they allow variables to be accessed from different methods, as opposed to `variables` (without the @ sign), known as **local variables**, that are local in scope and can't be read by different methods.

### Initialize

We can add an `initialize` method to run whenever a new object is made. It's automatic code that gets run without being called explicitly. Whenever you create a new instance of a class with the `new` method, `initialize` is automatically called the moment that object is created.

```ruby
class CoffeeCup
  def initialize
    @color = "white"
  end

  def color=(color)
    @color = color
  end

  def color
    @color
  end
end

my_cup = CoffeeCup.new
```
In the example above, when a new instance of CoffeeCup is created, it *automatically* has its color attribute set to `"white"`, because we set it in the `initialize` method. (This makes sense, because coffee cups are always white until they get painted!)

You can also set your `initialize` method to take in arguments. For example, when a new cup is created, it has a size from the start. That size is set by passing an argument like so: `CoffeeCup.new("Large")`. The parameters are defined in the  `initialize` method like so:

```ruby
class CoffeeCup
  def initialize(size)
    @size = size
    @color = "white"
  end
end

my_cup = CoffeeCup.new("Large")
```

### Object Actions

Not only do objects have attributes (characteristics), they also have **actions**. For example, you can have an action called `spill` on the coffee cup class that changes an attribute called `current_volume` to `"empty"` or `0`. Actions are methods that change the object itself or other objects that it interacts with.

```ruby
class CoffeeCup

  def current_volume=(volume)
    @volume = volume
  end

  def current_volume
    @volume
  end

  def spill
    @volume = "empty"
  end

  def fill
    @volume = "full"
  end

end

```

Let's Put it all together:
```ruby
class CoffeeCup
  def initialize(size)
    @size = size
    @color = "white"
  end

  def color=(color)
    @color = color
  end

  def color
    @color
  end

  def size=(size)
    @size
  end

  def size
    @size
  end
  
  def current_volume=(volume)
    @volume = volume
  end

  def current_volume
    @volume
  end

  def spill
    @volume = "empty"
  end

  def fill
    @volume = "full"
  end

end

```

Now, we can create a new coffee cup instance:

```ruby
 my_cup = CoffeeCup.new("Medium")
 my_cup.color #=> returns "white" because it is set in initialize
 my_cup.size #=> returns "medium"
 my_cup.color="red"
 my_cup.color #=> returns "red"
 my_cup.fill
 my_cup.current_volume #=> Returns "full"
 my_cup.spill
 my_cup.current_volume #=> Returns "empty"
```

Check out the resources section for more on Object Orientation!

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/hs-object-orientation-catch-up' title='Classes and Instances'>Classes and Instances</a> on Learn.co and start learning to code for free.</p>
