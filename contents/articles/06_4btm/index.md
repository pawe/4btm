---
title: 4 bit TM - Improving Reach
author: paul
date: 2015-02-23
template: article.jade
---

The last thing to make it generally useful is to get rid of that stupid distance and bandwidth limitations altogether. We haven't addressed chain breakers.

## Improving Reach

Sending more bits back in time than building time machine cores is nice. Wouldn’t it be even nicer to be able to send a message further back in time than a couple of nanoseconds, like for the party example mentioned before? Sorry, for keeping you hanging there.

This is not possible with a 2bTM. To illustrate this, think of what would happen if we just try. There would be corrupted bits, because we can not get rid of chainbreakers completely. We could however try to figure out when received data is corrupted. Let's use error detection for this.


## Error detection

If we have sent data and an error detecting code back for a longer distance, we just could make the logic resend it again and again until an error detecting logic said that's the right values. This wouldn't be workable because within longer distances the data (including the error detecting stuff) received would be almost completely random. Resulting in a lot of new time lines, which is not the issue we contain them anyway. The problem is found within the way error detecting works, it would say data is correct when it's not, i.e., "false positives". A bad thing.

An easy 5bit example? 4 data bits and one parity bit for error detection. The parity bit is calculated as follows: the ones from the data are counted. If this count is odd (1, 3) than the parity bit is `1`, and `0` if it's even. Data and parity bits need to fit together. Here are some examples:

	0000 0 -> good 
	0000 1 -> bad
	0010 1 -> good 
	0010 0 -> bad 
	0110 0 -> good
	0110 1 -> bad 
	1110 1 -> good
	1110 0 -> bad
	...

If the probability of two or more errors are high, something like this could happen: we want to send `0110` back. The parity bit would be `0`. Now two different values change by error, let's say the first two data bits producing `1010`, then the parity bit would still be `0`. The error detecting would compare the received parity bit and the calculated one and presume "positive" when it's actually "negative", i.e. a "false positive". 

	Send        Received (we can only see the received data)    
	0110 0      1010 0       

	                         Calculated parity bit from received data
	                         0  (1010 has 2 ones, 2 is even)
	
	                 ↓       ↓       

	                 Comparison of parity bits received and calculated
	                 0  ==   0    ✓  Data should be good
	
	↓↓↓↓        ↓↓↓↓

	Theoretical comparison of the data
	0110   ==   1010              ✗  but it isn't (and we can't find out,
                                                 because we only see 
                                                 the received bits)


This kind of error detection works only with an odd number of corrupted bits. There are [different and better suited algorithms][errdet] for this case, but the same fundamental problem occurs in all of them. 

The solution for our 2bTM we are left with is to stay within a distance where the likelihood of more than one error is low. The error detection is not free. The more bits we run the error detection on, the more time it takes. Time we must further reach back, which again increases the probability a false positive. An engineer should find the sweet spot.

This introduces another distance limitation, to overcome it we throw more hardware at the problem and add a second 2bTM, making it a 4bTM. The idea is, that we check the received bits from one 2bTM and put it in another, but only if the data is correct. If not, we resend it. The next graphic should illustrate how that looks.

![combining serialization repeating with error detecting][sereperr]

And with an error and resending:

![combining serialization repeating with error detecting][sereperr2]

We can now send very reliably a few bits back in time almost to when we turned  our time machine on. Not perfect, because it's still just a few bits. It's way less bandwidth to send back messages, like emails, pictures or videos.


## More Clocks and Containments

We basically apply the same tricks as before to increase bandwidth. Utilizing a clock, just this time with no extra time machine core. We just use one of the bits we have. If we have 4 bits we would use 1 as clock that gives us 3 remaining data bits. 

![same old tricks][4btmclock]

The growth of bandwidth is still limited. Every tick you get 3 bits. Let's say you let it run for `1024 ticks` before you read the message from the future. Then you get `3072 bits` or `384 bytes`. Way better, but still not much. You can either wait longer to increase your payload or add another containment with a "clock". Let's go for the latter. Why not?

From an outside perspective we have `3072 bits` to our disposal. Let's use 2 of them as a clock, which gives you 3 times the bandwidth grow per (outer tick). `00` is our default time line zero and if it differs, it's data, leaving 3 or 2<sup>2</sup>-1 (`01`, `10` and `11`) for actual messages send back.

	(3072 - 2) * (2^2 - 1) = 9204

Since we can choose how many bits we use for the clock generalize the above formula to:
		
	(3072 - n) * (n^2 - 1)
	
We can use this formula to find the optimal clock size. If you solve it, you get `2048`. With a `2048 bit` clock, we get `4294966272 bits`, or around `512 megabyte` per outer tick, which equal around 1024 inner ticks. If you factor in technical details, everything will become a bit different, but the general idea is still valid (enough).

The fun thing is, with that ~512 mb we can do the exact same thing by adding another containment: Solving `(4294966272 - n) * (n^2 - 1)` gives us a clock with around 2.8 billion bit clock. With this clock size, we get around 1467 yottabyte per tick. Notice that we haven't used more ticks and just exploded bandwidth. Clearly there are limitations, but they are coming from the implementation not the theory. Like so very often in engineering. Like I said, creating new time lines is cheap and we do so in a bit of a divide and conquer style. We just made creating und utilizing a couple quadrillions of time lines manageable.

For the real thing, you'd need a more complex setups. Like many things in this series, it's left out. Generally, there's a lot of potential to do better with different encodings and additional checks and corrections for chain breakers, the one explained is (as I believe) just the easiest to grasp. An obvious thing to add would be a higher-level error correction mechanism. 

We can now leverage the full potential of this time technology. The amount of sendable data is almost solely limited by information/computer technology connected to the time technology. Not time technology itself. What feels right. Also we increased the distance from nanoseconds to a very useful level. Party as long as we want! We should use it for natural catastrophe prediction before using it for parties, though.

It's time to think about an interface to our 4 bit time machine (4bTM). As an engineer, I don't need a fancy UI, something simple, already known would be good. The [next and last part](/articels/07_at-last) covers this. 


[sereperr]: 05_2x2btm.svg "Prepetition, Serialization and Error Detecting"
[sereperr2]: 05_2x2btm_error.svg "Prepetition, Serialization and Error Detecting"
[4btmclock]: 05_4btm_4bit.svg "Same old tricks. Just more timelines"
[4btmclockcont]: 05_4btm_4bit_containments.svg "Again, same old tricks. Just more timelines"
[errdet]: https://en.wikipedia.org/wiki/Error_detection_and_correction "Error Detection and Correction"

