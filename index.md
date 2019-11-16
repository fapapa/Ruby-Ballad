# Ruby, How Do I Love Thee, Let Me Enumerate the Ways

A ballad in four stanzas.

## [0]

Still in your youth, your Ruby cheeks glow

In an adept coder's hands, your methods they flow

Born in the land of the red rising sun

Your symbols, your strings, your classes, your "1"

Your procs, your nil, your lambda's too

All praise in unison, "I'm an object in you"

```ruby
> "Elizabeth Barrett Browning".object_id
=> 70237630268620

> 1.object_id
=> 3

> Proc.new { puts "Elizabeth Barrett Browning" }.object_id
=> 70237614019620
```

## [1]

With your father of SmallTalk, your mother of Perl

You speak with a Lisp, you iterate with a twirl

"Return, return," I beg, I implore

Render your value with every statement, every "for"

You keep not your expressions from yielding to me

Even an "if" has a value to see

```ruby
> no_way = if true
>   "yes, totally!"
> end
> puts no_way
=> yes, totally!
```

## [2]

The other fair maidens, be they Java or C,

Covet their operators, "They're for no one but me!"

"Use my plus, use my minus, use my multiply too,"

"As methods in your modules and classes named Foo."

"My built-ins are no better than your classes, my dude,"

"With special method names they may be imbued."

```ruby
> class Point
>   def initialize(x, y)
>     @x = x
>     @y = y
>   end
>
>   def +(other_point)
>     Point.new(@x + other_point.x, @y other_point.y)
>   end
>
>   def to_s
>     "(#{@x}, #{@y})"
>   end
> end
>
> point1 = Point.new(3, 7)
> puts point1
=> (3, 7)
> point2 = Point.new(2, 1)
> puts point1 + point2
=> (5, 8)

> class Playlist
>   def initialize(name, *songs)
>     @name = name
>     @songs = songs
>   end
>
>   def play
>     # logic to play the songs
>   end
>
>   def [](num)
>     @songs[num - 1]
>   end
>
>   def <<(song)
>     @songs << song
>   end
>
>   def to_s
>     @name + ': ' + @songs.join(", ")
>   end
> end
>
> my_list = Playlist.new("Faves", a_song)
> my_list << another_song
> puts my_list
=> Faves: Single Ladies, Truth Hurts
>
> my_list[1] = new_song
> puts my_list
=> Faves: Circles, Truth Hurts
```

## [3]

Mirrors, and smoke, and mystery are your shroud

Your methods and ways you jealously cloud

When first I attempt to write code that writes code

Trembling, shaking, and fearfully woe'd

Macro and method that gives birth to method

What is this black magic that leaves me but wretched?

To write code that writes… seems too hard to try

But gently you beckon, "Come, make your code DRY!"

```ruby
> class ActiveRecordClone
>   def initialize
>     @@table_name = self.class.name
>     @@field_names = self.get_fields_from_db_table(@@table_name)
>     make_getters_and_setters_for(@@field_names)
>   end
>
>   def self.get_fields_from_db_table(table_name)
>     # Connect to DB and run SQL query
>     # Return an array of field names for the given table
>   end
>
>   def make_getters_and_setters_for(field_names)
>     field_names.each do |field_name|
>       define_method(field_name) do
>         instance_variable_get("@#{field_name}")
>       end
>
>       define_method("#{field_name}=") do |value|
>         instance_variable_set("@#{field_name}", value)
>       end
>     end
>   end
> end
>
> class Product < ActiveRecordClone
> end
>
> p = Product.new
> p.name = "Pet Rock"
> p.price = 14.95
> puts p.name
=> Pet Rock
> puts p.price
=> 14.95
```

Ah, Ruby. Oh, Ruby. Are there any as fair?

You were created for beauty, with painstaking care

You are so much more than the sum of your parts

You're not just for Rails and online shopping carts

Yet "Python" they yell in the streets and the squares

Forlorn and forgot, your bed drenched with tears

"She wastes all our memory," goes the refrain

If you fix all those problems, will you surface again?

https://ruby-doc.com/docs/ProgrammingRuby/
http://rubylearning.com/blog/2010/11/23/dont-know-metaprogramming-in-ruby/
