---
title: "Bypass Facebook messenger download warning"
read_time: true
categories:  
  - guides
tags:
  - facebook
  - messenger
  - forced download
  - browser
  - bypass
  - android


---

Android users, rejoice! But not only Android users, anyone who has Chrome browser installed on their smartphone. Last month I announced that Facebook was pushing a new update onto their users: the messages screen was empty. You were no longer able to check messages on Facebook, but were presented with a link to download Facebook Messenger from Google Play.

However, there is a very simple way to bypass this warning and check your messages normally. 

<h2>What's the deal?</h2>

Facebook knows that you are accessing their website from a mobile browser. This means that you will be redirected to a mobile ready site **<a href="https://mobile.facebook.com"  target="_blank">mobile.facebook.com</a>**. However, you can simply type **<a href="https://facebook.com" target="_blank">facebook.com</a>** while **Request desktop site** on Chrome is active. Using this simple setting, you will be presented with the desktop site and not the mobile ready version of the website. Which means that you can access all your messages as normal.

Let us present the solution for the **Chrome** browser. Steps:

1. Go to settings (left button near the main Home button)
2. Check **Request desktop site** 
3. Access facebook.com again
4. Enjoy your new found bliss.

{% include base_path %}

{% capture fig_img %}
![Request desktop site on Android]({{ base_path }}/images/request-desktop-site-android.png)
{% endcapture %}


<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
  <figcaption>Request desktop site on Android</figcaption>
</figure>


---