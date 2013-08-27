---
layout: post
title: "Ruby Moku Moku Kai 2013/07/20"
date: 2013-07-27 18:27
comments: true
categories: [ ruby, meetups ]
---
Last weekend I attended the Nishiwaki.rb and Higashinada.rb Moku Moku Kai, held this month in Higashinada Kuminkan in Higashinada, Kobe. 

What is it?
-----------
Moku Moku Kai has been running since March with this being the fifth meeting and the fourth time I’ve attended. The format is simple, each attendee introduces what they are going to work on (usually development but sometimes research), they work on it for 2-3 hours and then introduce what they worked on with questions and occasional code review. 

This is quite different from the majority of programming meetups in the area which seem to be either study groups or follow a presentation format. The focus of Moku Moku Kai is on learning through doing and feedback from fellow developers — something which no amount of book-learning can provide. 

For a long time I’ve not had much exposure to developers outside of my own company, I did attend a few of the local presentation oriented groups but my own intravertedness combined with the format meant that I didn’t really connect with anyone there. The Moku Moku Kai has more interaction thanks to the small group size and the emphasis on feedback. It also has fairly active discussions in a private youroom group and post-meeting food and drinks, all of which contribute to a friendly atmosphere. A wide range of people attend, we have freelancers, startup founders, university researchers and salarymen who may or may not use Ruby in their work but everyone is focused on improving their Ruby skills. 

What I worked on
----------------
I did some development on my [tag_parser][tag_parser] project. This is a library for handling a simple message format I use at work. I started it when I hit a wall with what I could do with regular expressions. These were fine on a case-by-case basis but coming up with something general that would cover all the edge cases started getting hairy. I had heard about using state-machines for message parsing and knew about the [Ragel][Ragel] state-machine generator from an [essay][Ragel State Charts] by Zed Shaw. tag_parser uses Ragel to generate a tokenizer with some tests and surrounding code in Ruby.

Finishing up
------------
After everyone had finished presenting what they did we went on to a restaurant to eat and talk technical things. This is probably my favourite part of the event. I like hearing what everyone is up to and sometimes we have quite technical discussions.

If anyone is interested in joining the next MokuMoku Kai keep an eye out on [Doorkeeper][MokuMoku]. The events are in Japanese so it might be hard to participate if you don't speak the language but its worth a try if you’re interested and I’ll do my best to help with any language problems.

[tag_parser]: https://github.com/maikeru/tag_parser 
[Ragel]: http://www.complang.org/ragel/
[Ragel State Charts]: http://www.zedshaw.com/essays/ragel_state_charts.html
[MokuMoku]: http://nishiwaki-higashinadarb.doorkeeper.jp/
