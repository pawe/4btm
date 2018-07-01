---
title: 1 bit Time Machine
author: paul
date: 2014-10-18
template: article.jade
---

Last time we used a physical phenomenon to send one bit of information back in time. The distance (in time) was limited by design. We overcome this limitation by repeatedly taking the information from the future and send it further back.

## Chaining

First we make sure that the phenomenon repeats itself. We do so by firing a sequence of _p_ particles at one _T_, instead of just one _p_ like we did [before][the-basics]. Depicted in the next image. 

![Time Machine][expandingDistance1]

If you look closely, you'll recognize that the frequency in with the _p_ particles hit _T_ isn't randomly chosen. _p<sub>1</sub>_ is shortly before field _F_ when _p<sub>2</sub>_ is at the line of 'T'. This makes it possible to decide where _p<sub>1</sub>_ will go, depending on where _p<sub>2</sub>_ will hit _T_ or not. An event that occurs later in time. We do the same for _p<sub>2</sub>_. We decide to deflect _p<sub>2</sub>_ on whatever's _p<sub>3</sub>_ indication is. Then use _p<sub>4</sub>_ to decides _p<sub>3</sub>_'s path. Or a bit generalized: _p<sub>n-1</sub>_'s deflection is based on _p<sub>n</sub>_'s indication. As the information is passed on, in the end what will happen to _p<sub>1</sub>_ (in normal time, the first one) depends on _p<sub>n</sub>_ (the last one). An event in the past (_p<sub>1</sub>_ hit or not) is relying on something in the future (_p<sub>n</sub>_ indication). Because we can't do it manually we'll add a sensor, a circuit breaker that switches _F_ based on the sensors signal.

![Time Machine][expandingDistance2]


The sensor measures 'T', when it detects a hit for p<sub>3</sub>, the circuit breaker will switch the field off by tilting the small tilted line even more and cutting the power for _F_ off. Making p<sub>2</sub> hit too. As p<sub>1</sub> direction was based on p<sub>2</sub> it already hit _T_ and has bounced off already. The remaining question is how to get the information in and out of this little setup. Therefore, we add some more components.

![Time Machine][expandingDistance3]

To get the one bit information from the future, we only need to look at an early particle. For example, by looking at p<sub>1</sub> and what it does. Not too complicated. In order to put information in, we need to stop the chaining and determine if, e.g., p<sub>4</sub> should hit manually. It's done by an additional switch that takes away control from the sensor driven switching and gives it to one we can "manually" push (or not, depending on what information you want to send back).


As always, we'll leave out a bunch of technical problems, like how do we achieve fast enough switching time for _F_, achieve necessary _p_-frequency, fast enough computation if more than one target is used or how to take care of deflected particles so they won't disturb the whole process.


## Limited by Quality

Notice that the "distance" you can send information back in time is now limited by the TMs quality. Remember uncertainty from the first post? _p_'s can miss _T_'s or other disturbances can occur. One wrong indication breaks the whole chain and the probability of that happening increases with every _p_ passing.

Realistically we can reach now an area close to nanoseconds for transporting information back through time. We'll apply another set of techniques to further improve on this distance. Before we do that, we build something to play around and learn from in the [next part](/articles/04_using-it).


[expandingDistance1]: 03_expanding.svg "Expanding distance 1"
[expandingDistance2]: 03_expanding2.svg "Expanding distance 2"
[expandingDistance3]: 03_expanding3.svg "Expanding distance 2"

[the-basics]: ../the-basics