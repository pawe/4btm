---
title: Using a 1 bit TM
author: paul
date: 2014-11-18
template: article.jade
---

We are ready to build an interface to a 1 bit TM and then use it. It's still not powerful, but the knowledge we gain is vital.

## Simple 1 bit Time Machine

Setting up a background like this article has done so far is hardly found in popular time machine stories. The good reason for this is even if its presentation is reduced to its essence it's impossible to explain it in an exciting way to a larger audience. In the Sci-Fi (I'm familiar with) they usually state or imply the rules and build their stories on them. Sometimes they try to explain how it works but usually that ends strange.

So deriving just the rules for using a 1bTM isn't too complicated: Only a limited amount of information can be send backwards in time, not very far either (if you're lucky to the point in time where the machine had been started) and someone had/has to put that information into the machine.

Yet, having a strict and well-founded set of rules doesn't tell us what's going to happen when we use it. Only its use will. So let's exploit the previously explained effect and put together a simple 1bTM with a very easy to understand user interface: 

  * one On/Off switch, 
  * one Button, 
  * and one LED. 
  
When the button is pressed, the LED should light up before the button is pressed. Internally there's a 1bTM and some kind of logic assuring the described behavior. 


With that simple setup we can find out a lot about time, let's adapt the [Grandfather paradox][grandfather] to our simple one bit time machine. I generally don't feel like threatening or risking my or anyone's life for science, so here's my more harmless suggestion for an experiment. An agent looks at the LED at a certain point in time _t<sub>LED</sub>_ and if it lights up he doesn't presses the button (i.e. killing it), but if it doesn't he will press the button. In contrast to: the agent is going to kill my grandfather (makes the LED go out) and we'll see if I disappear (go out too). The next graphic should explain what happens step by step. For some reason scientist like to draw time lines  (__TL__s) upwards and this follows that norm thoughtlessly.

![using simple TM][usesTM]

Few things worth mentioning:
 
  *  It seems that we have created an infinite number of new "universes". Which is sad because I prefer Sci-Fi stories using the [self-consistency principle][selfconsist]. Talking about Grandfather paradox and self-consistency [Futurama][roswell] is coping that matter excellently.
  *  We really haven't created a infinite number of "universes". On a closer look you'll just find two different ones. For this setup, one can think of it like a unique set of "universes", which's maximum cardinality is bound to the amount of data the TM is able to transport (one bit -> two possible different "universes", 2 bit -> 4 "universes" etc.).

![using simple TM][cardinalty]

  *  It's really not a new "universe". As the information - LED lights up or not - is hardly affecting anything. It affects what it affects not more, not less. We'll make use of that later.
  *  There's no paradox in bootstrapping the whole process of forking time lines (__TL__s). What happens in the special _time line zero_ (__TL0__) is determined by the configuration of the time machine.


Times perception of a 1bTM user is still linear and there's nothing really new added to it, you already know switches, LEDs and buttons. What throws up the question how do we get this result? A harder and more complex research task which needs thus a more complex setup to answer. However, one heads up: the original time line zero can never know that TMs work. If not someone invents a essentially different TM.

On the opposite side that means TL0 is always safe from malicious use of 1bTMs. So I'm save even if I send a message back to the time my father wasn't received to hire a hit man to kill my grandfather. On a less serious issue of playing the lottery, it means that even if you send back the right numbers, your current self will never see a cent of that money. 

Instead of being sad about this severe limitation, let's look at it with the eyes of an engineer. How can we exploit this to improve our tech? We'll try in the [next part](/articels/05_2btm).

[simpleTM]: 04_simpletm.jpg "Simplest TM"
[usesTM]: 04_led.svg "Using the simple TM"
[cardinalty]: cardinality-of-timelines.svg "Just two timelines in our experiment"

[grandfather]: https://en.wikipedia.org/wiki/Grandfather_paradox "Grandfather Paradox"
[selfconsist]: https://en.wikipedia.org/wiki/Novikov_self-consistency_principle "Novikov self-consistency principle"
[roswell]: http://en.wikipedia.org/wiki/Roswell_That_Ends_Well "Futurama episode 19 of season 3"
