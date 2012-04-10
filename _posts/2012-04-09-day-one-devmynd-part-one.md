---
layout: post
category : apprenticeship
tags : [apprenticeship, devmynd]
---
{% include JB/setup %}

The title of this blog is a bit presumptive. Today I started as an intern at DevMynd Software, which is set to last for two months. <strike>If</strike> When I successfully complete that, I will be upgraded to 'apprentice.'

## What is DevMynd?

[DevMynd](http://devmynd.com/) is a software consulting company founded in 2010 by [Brad Wilkening](http://twitter.com/bwilken) and [JC Grubbs](http://twitter.com/thegrubbsian) (I originally had JC's name first, but Brad fixed that). [Peter Harkins](http://twitter.com/pushcx) is employee #1, which logically makes me #2 (insert jokes about interns/poo here).

## Round One, Fight!

Day one consisted of a standup at 8am at the DevMynd office, and me making Brad late for *his* standup at *The Client*. Peter doesn't work Mondays, and JC is currently on vaycay in Japan. Slackers.

I started off going through the technical tweets I emailed to my sexy new [DevMynd email](mailto:kori.roys@devmynd.com). One of them led me to this: "[Rails Isn't for Beginners](http://rakeroutes.com/blog/rails-is-not-for-beginners/)." I subscribed, and the penultimate post was "[Solve Online Ruby Puzzles With Rubeque](http://rakeroutes.com/blog/solve-online-ruby-puzzles-with-rubeque/)." I ended up doing that for most of the morning. Which reminds me. Check out my [review of Rubeque](http://koriroys.com/apprenticeship/learning/2012/04/10/rubeque-review/)! Some of the things I learned were:

+ Inject can have a default value. Useful if none of the enum elements pass the conditional in the block:
{% highlight ruby %}
  inject 0, :+
{% endhighlight %}
+ You can run [assertions in a block](http://rubeque.com/problems/nil-values). Probably better than typing out:
{% highlight ruby %}
 assert_equal 0,              nil
 assert_equal '',             nil
 assert_equal 'chunky_bacon', nil
{% endhighlight %}
+ You can use a [regex in the []](http://rubeque.com/problems/brackets-and-searches) after a string to search the string for said pattern.
{% highlight ruby %}
  assert_equal "hello world"[/e/], "e"
{% endhighlight %}

I also found [an exercise](http://rubeque.com/problems/baby-got-stacks) that I feel has poor tests (though the author's amazing rapping skills make up for it). The third and forth test simply allow me to push the whole array to the stack, then pop the whole array off and reverse it to get the tests to pass.

{% highlight ruby %}
class Stack
  attr_accessor :stack
  
  def initialize(input)
    self.stack = input
  end

  def pop(*args)
    return stack.pop if args.empty?
    stack.pop.reverse # This shouldn't work. Tests are incomplete.
  end

  def push(args)
    stack.push(args)
    true
  end

  def to_a
    stack
  end
end

stack = Stack.new([5, 6, 7, 8])

assert_equal stack.pop, 8
assert_equal stack.pop, 7
assert_equal stack.push([4, 2]), true
assert_equal stack.pop(2), [2, 4]
assert_equal stack.to_a, [5, 6]
{% endhighlight %}

Ok, fine. [Pull request submitted](https://github.com/daviddavis/rubeque/pull/89). We'll see if they agree with my analysis.

This post is now officially too long. Click next for part II.