---
layout: post
title: "Installing POW"
date: 2013-04-07 08:59
comments: true
categories: 
---
This is more just a reminder to myself than anything. To help out with rails development I'm going to try out [POW](http://pow.cx/). POW is a tool for Mac for running local instances of webapps on a Rack server with a meaningful url rather than localhost:xxxx.

How to get it:
```bash
$ curl get.pow.cx | sh
```
Which gives me:
```bash
Ps-MacBook-Pro:Development Owner$ curl get.pow.cx | sh
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  6887  100  6887    0     0   5802      0  0:00:01  0:00:01 --:--:-- 14498
*** Installing Pow 0.4.0...
*** Installing local configuration files...
/Users/Owner/Library/LaunchAgents/cx.pow.powd.plist
*** Installing system configuration files as root...
Password:
/etc/resolver/dev
/Library/LaunchDaemons/cx.pow.firewall.plist
*** Starting the Pow server...
*** Performing self-test...
*** Installed

For troubleshooting instructions, please see the Pow wiki:
https://github.com/37signals/pow/wiki/Troubleshooting

To uninstall Pow, `curl get.pow.cx/uninstall.sh | sh`
```

To set up an app to run with POW, make a symlink to it, like so:

```bash
$ cd ~/.pow
$ ln -s /path/to/myapp name_to_use_as_uri
```

The app should now be accesible via `http://name_to_use_as_uri.dev`

I didn't have a suitable app available so made a quick rails app:
```bash
Ps-MacBook-Pro:ruby Owner$ rails new arfarfarf
      create  
      create  README.rdoc
      create  Rakefile
      create  config.ru
      create  .gitignore
      create  Gemfile
      create  app
      create  app/assets/images/rails.png
      create  app/assets/javascripts/application.js
      create  app/assets/stylesheets/application.css
      create  app/controllers/application_controller.r
      ...
```

Then created the symlink like so:
```bash
Ps-MacBook-Pro:~ Owner$ cd .pow
Ps-MacBook-Pro:.pow Owner$ ln -s /Users/Owner/Development/ruby/arfarfarf/ arf
```

And was able to access the site immediately in my browser at `http://arf.dev`
