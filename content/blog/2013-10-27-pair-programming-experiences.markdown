---
path: "/2013/10/27/pair-programming-experiences"
layout: post
title: "Pair Programming Experiences"
date: "2013-10-27T14:52:00.000Z"
comments: true
categories: 
- ruby
- pair-programming
- nishiwaki.rb
---

So, the last couple of Nishiwaki.rb and Higashi-Nada.rb meetups have been pair programming sessions
under the title of [Pair Programming in Action](http://nishiwaki-higashinadarb.doorkeeper.jp/events/6514).
Last month was in Ono city (relatively) close to Nishiwaki and this month
we were in [Cahootz](http://cahootz.jp/) in Kobe.

For Pair Programming in Action the group divided into pairs of a more experienced rubyist with a less experienced one.
We then voted on a programming problem to work on so the whole group would be working on the same problem (unlike MokuMoku Kai
where everyone does something different). Last month we did the Mastermind game used as an example in The RSpec Book and this
month we did [ゆっくり座りたい〜](http://nabetani.sakura.ne.jp/hena/ord7selectchair/) which is a problem about seating order.
Both problems are presented in a format ideal for Test Driven Development (TDD) with expected outputs for different inputs that
exercise all the edge cases of each problem. This makes it easy to proceed one step at a time, first writing code that produces
the correct output for the simplest case and then gradually moving on from there.

Pair programming is unsurprisingly a very sociable experience. Two people work together with one person "driving"
(writing code) and the other "navigating" (watching for mistakes, giving feedback and direction and asking questions).
You take turns in each role swapping whenever you feel like it. The atmosphere is very different to the MokuMoku Kai meetings
that we usually do (MokuMoku literally means to do something quietly) with everyone talking at the same time.
I remember a few occasions when someone tried to address the whole group and we just kept on going anyway (sorry Aki-san!).

In each of the Pair Programming in Action sessions we made sure to pair with someone different from before.
It was interesting to see how much of a difference having a different pair makes. Everyone has a different approach to things
and a different communication style. From my first pair I learnt a lot about the core ruby libraries and some git commands.
From my second pair I learnt about some useful tools (tig) and environment settings.

One pain point was switching roles. We each used our own laptops rather than working together on one (which would have been
too cramped and awkward). This meant that when we wanted to switch roles the driver would push their changes to Github and the new
driver would pull those updates. This is fine if the switch occurs when all tests are passing but sometimes its nice to switch
in the middle of a problem when one person has an idea that is easiest expressed in code. As a result I've started looking into
remote pair programming.

I went into both of the pair programming sessions without any preparation. I'd heard about pair programming before and even done
some casual pair programming at work but I hadn't thought about or researched how to make the most of the experience.
Based on the little research it looks like I might have missed some things - such as the particular roles of the driver
and navigator and what each is responsible for. I'm looking forward to having another go but in the mean time I think I'll do
some reading on the topic:

* [How to Pair Program](http://www.wikihow.com/Pair-Program)
* Remote Pair Programming Resources at [PairProgramWith.me](http://www.pairprogramwith.me/)
