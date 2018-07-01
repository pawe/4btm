---
title: The Basics
author: paul
date: 2014-08-18
template: article.jade
---

I'm sorry; this is necessary. What's described in here is what you should be 
looking for in nature, if you wanted to build a time machine. Well, one type of 
time machine — a 4bTM.


## Physical Phenomenon

Everything engineered is built on phenomena found in nature. To describe the 
phenomenon enabling a 4bTM, we'll use the flying-dots explanation model.

![Physical Phenomena Part 1][phsphe_wf]

You see two dots. One smaller particle - _p_ - shoots at a larger target - _T_. 
If you don't look at it very closely, _p_ hits _T_ and then bounces off. Pretty 
much what one would expect from it. However, if you look very closely you can 
see that shortly before _p_ touches _T_, the letter 'T' in _T_ goes red for a 
moment, signalizing that it knows that it's going to get hit. The 'T' going red 
stands for a measurable property of _T_. So far, not very exciting, it's like 
knowing an asteroid is going to hit Earth's atmosphere and 'foreseeing' a 
shooting star. There's a line ("line of T") to indicate where _p_ needs to be, 
when 'T' gets red. This illustrates _T_'s range of sight.

Now for the interesting part, because we can influence where _p_ is going. We 
already gave it a direction by purposely shooting it at _T_. The question is, 
what's going to happen if we try to deflect its path after it already passed 
the slashed line. Let's use a field _F_ for that. 

![Physical Phenomena Part 2][phsphe]

So, step by step, what happens is:
 * _p_ is flying towards _T_ so it will hit _T_
 * at the time _p_ passes the "line of T" we look at the 'T' of _T_ (red or not 
 red, in the picture above it doesn't go red)
 * _p_ flies further in the direction of _T_
 * shortly, before it's too late to deflect _p_, we put on field _F_
 * _p_ gets deflected and misses _T_ 
 * we already knew that because the T in _T_ wasn't red when _p_ passed "line 
 of T".


This is interesting, because it works even if the decision to deflect _p_ is 
made after _p_ passed the "line of T". In short, that's the "magic" which gives 
us information about our future action (deflect or not). It's truly astonishing 
and truly limited to a very very short period of time. We will work on that 
limitation.


## Realities

In a perfect world, the two values would coincide with each other no matter how 
often we repeat this experiment. We would always gain valid information about 
what's going to happen in the very very immediate future. As you probably know, 
the real world usually doesn't let us exactly rebuild such a heavily simplified 
model. It's the same here, e.g. the particle _p_ could miss or hit its target 
_T_ when it shouldn't. Basically, this is because our aiming and/or deflection 
with _p_ is flawed and therefore _p_'s path isn't what it is supposed to be. 
Secondly, _T_ isn't in the area where we need it to be. Another example could 
be that the measuring of this "T goes red" property is flawed.

Keeping _T_ where it is, is one problem to solve; the aiming and deflection of 
_p_ is another one and believe me there're many more. The core issue, though, 
is how to expand that time to something useful for humans. This is what the 
rest of this series of articles will focus on, after giving you an idea why the 
phenomenon doesn't need to be perfectly deterministic.

One practical approach to improve the accuracy of _T_'s indication is through 
parallelism. Instead of one pair of _p_ and _T_ we set up a couple of them and 
average out measured results. Through averaging we gain accuracy, at the cost 
of setting the same thing up multiple times.

![One way of dealing with false measurements][threepara]

Mean of three parallel _T_'s:

 * 3 _p_'s are flying towards 3 _T_'s
 * at the time the _p_'s pass the "lines of T's" we measure the 'T' of eachh _T_
 * this time, we don't put _F_ on because we want them to hit
 * two _p_'s hit, one misses 
 * the mean of all three measurements still indicates a hit

With a parallelism of three, one measurement can be wrong. Now imagine many 
more of these _p_ - _T_ combinations. Then only half of them minus one can be 
wrong. Meaning that we theoretically only need a greater than 50% accuracy of 
this phenomenon. Practically, it needs to be more but the good news is, for the 
thing we're building here, it need not be 100 percent. There are other tricks 
we can and will apply to mitigate uncertainty.

Overall, knowing what one bit (hit or no hit) will be in a fraction of a moment 
doesn't seem to be very helpful, but as already mentioned, we'll deploy some 
tricks to expand that.


## Science 

This is an engineering approach on time machines, and as such, it will not 
cover any theories actually discussed by physicists and will not try to fit 
into existing scientific theories. We assume the described phenomenon as given 
and build up on it to create something useful for humans. The engineering part 
of time technology.

If you're interested in the theoretical parts, you might enjoy commencing your 
endeavor over at Wikipedia's article about [Retrocausality][retro]. This series 
continues with a [use case](/articles/02_a-use-case/).



[phsphe_wf]: 02_without_field.svg "Physical Phenomena we use later to build a TM Part 1"
[phsphe]: 02_with_field.svg "Physical Phenomena we use later to build a TM Part 2"
[threepara]: 02_error.svg "One way of dealing with false measurements"
[retro]: https://en.wikipedia.org/wiki/Retrocausality "Retrocausality"