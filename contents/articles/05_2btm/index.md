---
title: 2 bit TM - Improving Bandwidth
author: paul
date: 2014-12-03
template: article.jade
---

Let's put the knowledge we gained from using the simple 1 bit TM to work and start improving it.

## Improving Bandwidth

By now, we have a physical phenomenon that could be found by a team of researchers. As a Sci-Fi fan I suppose that these researchers were looking for such an effect because they were inspired by Sci-Fi. Next we explained how new physical knowledge helps to get information about the very near future and that we have control over this information. Someone has to think of that. Then we made it more useful by extending its range with chaining the phenomenon.  Another idea someone had to put to work.

We have left out a lot of technical breakthroughs (that had to be made to see it actually work) there is one major improvement we shouldn’t overstep. That's utilizing the experience of TMs first uses. To be more precise it's one aspect that was already mentioned but hasn't been pointed out very well yet. Remember that stupid tautology: information sent through a TM affects what it affects? Now we exploit that we have actual control of what's affected.

 
Controlling what a TM affects is really a lot easier than it sounds. Let me show you by advancing the simple TM by adding some internal memory. Replacing LED and Button with an interface where we can connect an electronic device (e.g. a micro-controller). And adjusting the controller logic so it can leverage the added memory.


## Serialization

Wouldn't it be nice to be able to send more than just one bit back in time without the hassle of building many 1 bit TM cores? Setting up a single 1 bit core does require a huge amount of effort. Then we would do what's cheap, in our case that's creating new time lines (TLs). However, and this is important, we carefully control how they look. For most of the TLs created we will "contain" them within this advanced 1bTM. The TLs actually affecting the outside world will only by accessible through a well designed interface.

![serialization of data][serialization]


This seems to work properly if the data the 1bTM receives from a Computer in every internal TL is the same. With no interference from the created timelines to the outside this is a valid. The problem lies somewhere else and is quite fundamental to this kind of time machines.

Used to continuous time, there is one thing we never had to ask ourselves before but is crucial for this feature. _How do we know in which TL we are?_ Or more detailed: Let's say the first bit is configured to 0 then we want to send back 0 too. When we measure it, do we read the configured value or the one send back in time? 

If I send you a regular message containing 0 or 1 you do one thing when you get a 0 and another when getting a 1. 
With TM bits: I send you a message. You always read that message at the same exact time.  It's 0, if I use the TM then I can change that to 1. I can however not send you 0 back and tell you that's the message I have send you from the future.

Or in other words, if 0 is configured and we send back 0, we end up in the same timeline. Meaning we haven't created a new time line. Because we already read a 0.

![wont work][problem]

A similar problem occurs if we do electrical encoding of signals with, e.g., false encoded as 0 volt and true as 5 volts. When sending a false over the line but the default voltage on the line is 0 volt too, then the receiver doesn't see a difference when you send it. There are conceptually two solutions to this. One where we add a clock signal, determine when to read, or use a signal change to encode the bits send over the line instead. A signal change is a change in voltage over time. Since we're building a time machine, we hardly can exploit a change over time.

So in the context of this TM, bits are a slightly different to computer bits. Our adaption to this, even it's expensive, results in upgrading our TM with another 1 bit core (making it a __2bTM__) and use the second core as a "clock". 


## Clock

The "clock core" determines if the received bit is the value send back. This is done by setting its default value to _false_ (0) and chance it to _true_ (1) when the actual value is put onto the other core. So when the controller reads both values, he can check the clock first. If its _false_ he does nothing, if its _true_ he increases an index by one and resets the clock core back to _false_.


![serialization done right][serialization2] 

This is repeated for all bits that are send back. Then, when the last timeline is reached, the controller sends the data to the outside. As all the other created timelines are contained within, there is no effect to the outside world. So the data we read in the future is the same in all internal time lines. We just need to know which bit of the message has to be send back in each internal timeline.

Introducing a clock also means we can not send information further back than to the moments when we set/reset the clock. Theoretical, we could set it for a long time. If we take chain breakers into account it's not possible anymore. The further we reach back the likelyhood of a wrong indication increases. Before we takle this problem in the [next part](/articles/06_4btm), let's simplify our diagrams.

![simpler drawing][simpler]


[serialization2]: 05_serial_2cores.svg "Serialization done right"
[problem]: 05_serial_problem.svg "There is a problem"
[serialization]: 05_serial_try.svg "Serialization"
[simpler]: 05_no_clock_in_drawing.svg "Let's make our lifes easier"