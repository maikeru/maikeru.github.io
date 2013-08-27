---
layout: post
title: "Ascii Sort"
date: 2013-08-27 22:21
comments: true
categories: [ruby, sorting, ascii]
---
*Note: The code described here is that committed to Github on Aug 16, 2013*

If you have a look at my Github Repositories you'll see I've added a new project called [Ascii Sort](https://github.com/maikeru/ascii_sort). This was my project for this months local Ruby Meetup (the Moku Moku Kai I reported on [last month](/blog/2013/07/27/ruby-moku-moku-kai-2013-slash-07-slash-20/)). I'm quite happy with how things turned out so I want to talk about it a little.

One of the difficulties with Moku Moku Kai is choosing something to implement that can be implemented in the 3 hour coding period. A lot of my early attempts were too ambitious leaving me with little to show the group after the time was up. 

I settled upon writing a sorting algorithm but that didn't feel like it was big enough so I decided to also output a visualization of the sort as it progressed to the console.

Bubble Sort
-----------
Bubble sort is a simple sorting algorithm that looks at adjacent pairs of items in the list and swaps them if the first item in the pair is bigger than the second, looping around again until the entire list is sorted. Here's an example of the first pass through a reverse-sorted list.

reverse sorted list as a starting point:

    a ####
    b ###
    c ##
    d #

a > b so swap them:

    b ###
    a ####
    c ##
    d #

a > c so swap them:

    b ###
    c ##
    a ####
    d #

and finally a > d. We have reached the end of the list so that's the end of the first pass

    b ###
    c ##
    d #
    a ####

There's a more detailed explanation (and nifty animated gif) on [wikipedia](http://en.wikipedia.org/wiki/Bubble_sort)

The Implementation
------------------
I knew I wanted the sorter class to call out to a Listener object after each step of the sort. In the case of bubble-sort, this would mean calling the listener after each a pair of values was assessed but before moving onto the next pair of values.

I started off by implementing the sort test-first but couldn't quite get my head around it. I was trying to think of everything at once: how to implement the sort, what would be the most idiomatic ruby, what would be the best way to write the tests etc. This was too much pressure and, as I mentioned above, there was a time-limit so in the end I implemented the core algorithm first and then went back and fixed the tests. 

With the BubbleSorter class implemented, the next step was to Implement a visualizer. By this point there was only about half an hour of coding time left. When I implemented the sorting algorithm I had made a simple driver (called runner) to check that things were working as expected. As there wasn't much time and I wasn't sure what I was doing I did a quick implementation of a visualization class inside runner. Each number in the partially sorted list is represented as a line of "#" characters of variable length and the console is cleared and the list redrawn every time a step completes. I even added some color in the last five minutes.

Here's some actual output!!

**Sort in progress**

{% img /images/ascii_sort_in_progress.png %}


**The finished sort**

{% img /images/ascii_sort_complete.png %}


Post-Mortem
-----------
Now that I've had some time to think about it (and having implemented it once already) I would go about things differently if I was starting again from scratch. First I'd just focus on the algorithm implementation, proceeding test-first by writing three tests:

1. An already sorted list
2. A reverse sorted list
3. A "random" list

Each case would check that the final result of the algorithm is a sorted list. Once the implementation was complete and the tests all passed I'd move onto the listener functionality. This would need a separate test using a mock-listener object to record the data passed in each time the listener was called. If I know the starting list I can predict exactly what the partially sorted list will be at each step so I can test that. The main point of this test would be to verify that the listener was being called at each step rather than the details of the sorting algorithm. To keep that focus the test would use a short input list so that the listener would be called only a few times. 

For the visualization class I think writing it the way I did was useful as a prototyping exercise so I'm not sure I would change that approach. However, it is just a prototype and the next step is to rewrite it in it's own file and driven by tests.

What Next?
----------
Next I want to test drive some(?) different visualization classes with different visualizations of the same sort algorithm. Once that's done I'd like to add at least one more sorting algorithm. Finally, with multiple sorters and visualizers available to combine together I want to make a command-line program with switches to select which visualizer/sorter combination to use.
