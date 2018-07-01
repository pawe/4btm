---
title: A Use Case
author: paul
date: 2014-09-18
template: article.jade
---

If we build a time machine, we should first know what we are building it for. 


## Party

Really smart people like Stephen Hawking [joke][ars-hawking] about experimental 
evidence that time travel isn't possible. You can do that experiment yourself: 
throw a party, but send out invitations to time-travelers after that party. See 
(or already) know who showed up. You'll find something similar in the TV show 
"The Big Bang Theory", where Sheldon states:

> "Anyway, it occurs to me, if I ever did perfect a time machine, I would just 
go into the past and give it to myself thus eliminating the need for me to 
invent it in the first place."

But what if it's possible to build a time machine, but you just have to use it 
properly, i.e., not by sending the invitation to people you think can travel 
through time, but rather, sending the invitation back in time. Mr. Hawking 
would still be right; it wouldn't be time "travel".

In that vein, lets paraphrase the party experiment to a problem that can 
actually occur in real life. Or do you know any time travelers?. Here's the 
example: during a party you realize that you have forgotten to invite a group 
of people whom you really liked to be here, but they are now too far away to 
get here in time. Wouldn't it be awesome to correct this mistake by sending 
invitations back in time? So you and __all__ your friends could spend some 
quality time together?

The difference is: with this approach, information goes back in time, not 
people (or matter in general). It needs to be encoded somehow, though. 
Forgetting about scale of time for one moment we could exploit the [previously 
described phenomena][basics] to solve our problem like this: 

It's Monday and you want to invite the guy's to a boy's night out on Wednesday 
but you're not sure about the just men part. So what you could do is:

  1. On __Monday__ you set up a particle _p<sub>GIRLS</sub>_ aiming at a target 
  _T<sub>GIRLS</sub>_. _p<sub>GIRLS</sub>_ should pass the "line of 
  T<sub>GIRLS</sub>" on Tuesday. On the same day, you turn on _F_, so if we do 
  nothing 'T' of _T<sub>GIRLS</sub>_ won't go red.

  2. On __Tuesday__ you send the invitation to your male friends. Then you look 
  at the 'T' of _T<sub>GIRLS</sub>_ very closely, if it does go red you also 
  send invitations to the girls.

  3. On __Wednesday__ you go out and party with your friends.

  4. On __Thursday__ you recap the evening and if you come to the conclusion 
  that it would have been more fun with the girls also in attendance, you turn 
  off _F<sub>GIRLS</sub>_. This would result in the 'T' on _T<sub>GIRLS</sub>_ 
  to have gone red on Tuesday, what should have made you send out invitations 
  to the girls on Tuesday.

![Time Machine][party]

Instead of doing it just for all 'girls' together, you could do it for every 
single person in your contact list. Send invitations like you would do 
normally, and at the same time set up a pair _p<sub>FRIEND</sub>_ and 
_T<sub>FRIEND</sub>_ for everyone you know and haven't invited. Then engage 
someone looking at the 'T' on every _T_ and if a 'T' does go red to deliver an 
invitation to the associated person. Next you are partying with no worries, and 
if you find out you forgot someone, turn the field attributed to that specific 
person off. 'T' on that person's _T_ has gone red, so that person should have 
already got an invitation. 

Nice, right? Except that we ignored scale of time. It takes _p_ only a fraction 
of a small part of a second to get from "line of _T_" to the point where it's 
too late to turn off _F_ and not half a week.

To increase the theoretical time, so we'll be able to party a bit longer, we'll 
chain this effect. The [next post](/articles/03_1btm/) will cover this in more 
detail.


## Takeaways

As a fan of "The Big Bang Theory", I'm sorry that Sheldon is wrong (with not 
perfecting time machines for the reason of him being able to go back in time). 
In fact, with this kind of TM, he would have to set it up first in order to 
then send his findings back in time to himself - so he wouldn't be able to 
avoid the work in creating a TM.

So far the bottom line is this: we're using a physical phenomenon that shows us 
the future — or one bit of it. Just information though - nothing physical. 
However, we need to set up the whole process before we can read a bit from it 
and we need to give that bit a meaning and act conditionally on it. Girls or 
no girls!


[party]: 03_party.svg "Party" 
[ars-hawking]: http://arstechnica.com/science/2012/07/steven-hawking-on-time-travel-m-theory-and-extra-terrestrial-life/ "Arstechnica Interview with Stephan Hawking"
[basics]: ../the-basics/
