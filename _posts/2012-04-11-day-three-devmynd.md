---
layout: post
category : apprenticeship
tags : [apprenticeship, devmynd]
---
{% include JB/setup %}

## Round Three, Fight!

Day two began at 10am with me downtown pairing with [Joe Hirn](http://twitter.com/jhirn) at *The Other Client*, where I also met Tyler, Frank, and Ryan. Most of the morning was spent getting me onboard to the project. I kept track of everything we did, from cloning the git repos to what brew packages we use. I plan to use that to write a readme tomorrow so that anyone new to the project can just reference that and get up to speed quicker.

In the process of getting up and running, Joe gave me bonus points for running rbenv, and for already having Imagemagick installed. We found that two of the repos didn't have a .rbenv-version file. So I copied those over from the third repo, and got to ring the first-commit bell.

Joe was beating his head against the wall trying to get bundler to stop breaking. I asked him what the problem was, and he said that some gems weren't playing nicely together. I asked him if rather than explicitly requiring carrierwave, could he just let it get pulled in as a dependency? He tried it, and it seems to have fixed his issue.

Frank was whiling away the hours on a rake task to update images. It was throwing him a nasty error though, so Joe came in and cleaned up quite a bit of the code. Made it easier to read, and eventually the error exposed itself. We were trying to set the 'belongs_to' field for images by doing this:

{% highlight ruby %}
  Player.all.each do |p|
    if p.belongs_to.nil?
      if Team.has_player(i.id).first
        Team.update_ attribute(:belongs_to, "Team")
      end
    end
  end
{% endhighlight %}

We stared at that one a while before realizing it should look more like this:

{% highlight ruby %}
 Player.all.each do |p|
   if p.belongs_to.nil?
     if Team.has_player(i.id).first
       i.update_ attribute(:belongs_to, "Team")
     end
   end
 end
{% endhighlight %}

Yeah, stupidly obvious when looking at it now. Oh well.

I learned a little about named scopes. So far my understanding is that they are basically methods for queries chunks. I was also introduced to solr + sunspot + lucine. And by introduced I mean they were mentioned and I haven't researched them as yet.

{% highlight ruby %}
  brew tap
{% endhighlight%}

Look it up. It's actually pretty cool.

At 6pm I migrated to Enova for the Ruby Hack Night. I met [Corey Haines](http://coreyhaines.com/) on the train and we ended up pairing to do the night's exercise. Corey is a great teacher, and we had a lively discussion as to how to go about TDDing [this exercise](http://puzzlenode.com/puzzles/3-spelling-suggestions). We scrapped it once and started over, and the second time it went rather well. I learned about the each_cons method from Corey, and what triangulation means in relation to testing. We didn't completely solve it in the two hours, but I have no doubts Corey could have if left to his own devices.