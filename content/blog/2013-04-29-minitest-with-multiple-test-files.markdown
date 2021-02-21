---
path: "/2013/04/29/minitest-with-multiple-test-files"
layout: post
title: "Minitest with Multiple Test Files"
date: "2013-04-29T11:31:00.000Z"
comments: true
categories: [Minitest, Rake, Ruby]
---

I started using [Minitest] for the [Game of Life] code kata.
I like how simple minitest is - you can do anything with assert and with a [cheatsheet] its easy to write tests however you like. I now have a grand total of two test files and would like to run them both. So far I've been running tests like this:

```
ruby tests/name_of_my_test.rb
```

But this only works with single files. The obvious next step:

```
ruby tests/*.rb
```

doesn't work as ruby will only take one file as an argument.
The top search result lead me to [Rake::TestTask].
This was the first time for me to write a rakefile and I'm not very experienced with Ruby so there were a few hiccups along the way. My final working rakefile looks like this:

```ruby
require 'rake/testtask'

task default: [:test]

Rake::TestTask.new do |t|
  t.libs << "tests"
  t.test_files = FileList['tests/*tests.rb']
  t.verbose = true
end
```

[minitest]: https://github.com/seattlerb/minitest
[game of life]: https://github.com/maikeru/Kata-s-and-Puzzles-in-Ruby/tree/master/game-of-life
[cheatsheet]: http://mattsears.com/articles/2011/12/10/minitest-quick-reference
[rake::testtask]: http://rake.rubyforge.org/classes/Rake/TestTask.html
