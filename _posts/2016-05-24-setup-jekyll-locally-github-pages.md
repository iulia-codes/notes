---
title: "Setup Jekyll locally"
read_time: true
header:
  overlay_image: heimat.jpg  
categories:  
  - guides
tags:
  - jekyll
  - github
  - pages
  - setup

#modified: 2016-05-29T11:39:01-04:00

---

Setting up Ruby for the first time, can be a challenging task. Especially if you are trying to do that on Windows, and with an existing project which you do not know. And a programming language that you do not know. But with time and patience, everything can be done.

Github pages are really powerful at offering free hosting, given that you use Jekyll, which is a static website generator.

I come from the Wordpress world, which I do honestly love with all my heart. However, setting up Wordpress for a small website, was not something I had in mind. And the functionalities that I needed are available for free.

Here I am now, one day after, with the instructions on how to setup your own Jekyll blog on Windows. For Linux and MAC, there are other instructions and possibly, a plethora of information on the web.

Given the flavours of developer tools out there, this tutorial is intended for my current setup. Here is my environemnt setup:

* Windows 8.1 x64
* Sublime Text Build 3114


<iframe width="640" height="360" src="https://www.youtube-nocookie.com/embed/t9qDNe7xk4c?controls=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

```ruby
GUIDE TO INSTALL RUBY 2.3 ON WINDOWS x64 AND RUN YOUR FIRST JEKYLL WEBSITE IN LESS THAN 30 MINUTES

Requirements:

Ruby 2.0.0. or higher
DevKit
Bundler

1) Install Ruby 

http://dl.bintray.com/oneclick/rubyinstaller/rubyinstaller-2.3.0-x64.exe

Choose Add Ruby executables to your PATH.

Verify Ruby executable is added to your PATH (otherwise restart your computer)

2) Install DevKit 

! Important: the version of DevKit must match the version of installed Ruby 

x64-> x64

Switch to DevKit root folder and run in the command line:
Step1)
ruby dk.rb init
Step2)
ruby dk.rb review

If at review the invalid configuration is given, edit the file config.yml manually. Jump to Step 2.1)

Step2.1) In the config.yml add the path to your Ruby installation.

Step3)
ruby dk.rb install 

3) Install your local Jekyll site

Download the website from the Github page

https://github.com/mmistakes/minimal-mistakes/

4) Update gems & install Bundler & Jekyll

Install Bundler, run:

gem install bundler
If Windows wants to connect to  the network through firewall, allow it.

The website we downloaded, already have the Jekyll settings inside. Verify them in Gemfile.

Step1) Install dependencies with Bundler

bundle install

This step here is tricky, as it failed for me and it required a lot of troubleshooting. Let's see.

It usually was crashing at installing wdm 0.1.1. with native extensions. This was because I was using different version of Ruby and DevKit.

nogokiri error fix:

StepFix1)
Update nokogiri version

Open Gemfile.lock and change nokogiri version from 1.6.7.2 to 1.6.8.rc2 

This updates to the latest version
( http://stackoverflow.com/questions/36868318/nokogiri-requires-ruby-version-2-3 )

Delete 

    nokogiri (1.6.7.2-x64-mingw32)
      mini_portile2 (~> 2.0.0.rc2)


StepFix2) Jump to Step1)

5) Build your local Jekyll site

In the command line run:

bundle exec jekyll build

Wait until it runs, this may take a little while.

6) Run your local Jekyll site

In the command line run:

bundle exec jekyll serve

The website is now running at 

http://127.0.0.1:4000/minimal-mistakes/

7) Modify your local Jekyll site

Add posts into the _posts section.

For more details, observe this link. https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/

Congrats! You have now setup your own Jekyll site locally, with Github pages, in less than 30 minutes!
```
---
