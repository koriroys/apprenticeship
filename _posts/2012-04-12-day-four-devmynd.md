---
layout: post
category : apprenticeship
tags : [apprenticeship, devmynd]
---
{% include JB/setup %}

## Round Three, Fight!

Today took me back to *The Other Client* to get some work done and pair up with Joe. 

I met Alex again, who I first met at code and coffee on Tuesday, when he stopped by to show his friend our office. I feel back because I forgot his friend's name, and I'm usually good with names. It starts with a J, I think. I also met Charles, Vince, and Kristen from Mentor Mob, but only briefly.

Today I was assigned what should have been a simple card: add a loading spinner to a page that runs whenever ajax is running, and stops when the ajax finishes. Joe pointed me to the right resources, and while it probably should have only taken me a half hour or so, I had to learn HAML and the right jQuery calls to complete the task.

After a little stumbling around, I had something hacked together, and Joe looked at it. 'Good nuff,' he said, so at that point he educated me about using

{% highlight ruby %}
  git pull --rebase
{% endhighlight %}

It makes the commit log very linear, which I'm told is a good thing. I think I buy it. I also learned about HashWithIndifferentAccess, which lets you do this:

{% highlight ruby %}
  a = HashWithIndifferentAccess[:a => "Joy", :b => "Honor", :c => "Risk"]
  a[:c]  # => "Risk"
  a['c'] # => "Risk"
{% endhighlight %}

Pretty cool if you ask me. It came up because Joe wanted to write a method to convert two arrays into a hash, and I showed him that you can do this:

{% highlight ruby %}
  a = ['one', 'two', 'three']
  b = [1, 2, 3]
  
  Hash[a.zip(b)] # => {"one"=>1, "two"=>2, "three"=>3}
{% endhighlight %}

He wondered if HashWithIndifferentAccess could do that too, and it turns out it can. Thanks [Ruby Trick Shots](http://rubyreloaded.com/trickshot<div></div>s/)!

The rest of the day I just sat and watched Joe rip through a card that involved some major surgery on one of the controllers, and lots of code deletion. In the process I was given a cursory introduction to Emacs. It's actually turning out to be useful, because I'm using some of the tips I picked up to navigate Textmate without using arrow keys, and those same bindings work in terminal too.

My homework is to watch [Strange Loop](https://thestrangeloop.com/) talks like [Simple Made Easy](http://www.infoq.com/presentations/Simple-Made-Easy) or [We Really Don't Know How To Compute!](http://www.infoq.com/presentations/We-Really-Dont-Know-How-To-Compute), as well as find the SICP lectures by Gerald Sussman and watch those.

After worked I attended the Code Academy mentor/student meetup, and met some new faces. Laura Stude, Ilana Milkes, Larry, Scott Hughes, Tolu Bukola, Jennifer Dudley, Brendan Hennessy, Chris Bolton, Ezekiel Binion, Frank Fukuchi, Nakyum Yoon, and Ted Meeds. Also saw some familiar faces: Emily Ellison, Dave Woodall, Roman, Greg Cardoni, Tom Cullen, Josh Mangoubi, Brad Wilkening, Vince Cabansag, Arvin Dang, Dan Lavin, and Ralph Wintle.

Finally, to wrap up the night, Josh Fabian and Justin Tallant, my roommates and current students at Code Academy, showed me a project they worked on for class. I sat down with them and showed said what I liked about it, and then we hit it with the refactoring stick. I showed them how to break up a method into smaller methods, how to refactor a loop with an external sum variable to use map instead, and then inject to get the sum of the elements. We then talked about why you should separate code that just displays information into it's own method, which lead to a discussion about whether or not you'd die from dehydration or lack of sleep first.

I told Justin to stop drinking and stay up all night and see which one he dies of first. He declined. Guess I need a new guinea pig.