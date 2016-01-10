---
layout: post
title: Setting Up Onedrive Academic on OSX
modified:
categories: blog
excerpt:
tags: []
image:
  feature:
date: 2016-01-10T18:14:37-05:00
---
According to the web portal for my OneDrive, I was supposed to be getting 1 TB of storage, but when I logged into the OneDrive app on OSX I found myself sitting with 15 GB of storage.

![Total](Amount)

When I looked at the app, it turns out I was logged into a personal account that was created using my academic email.

![Personal Account](Personal)

It turns out the fix for this is easy simply type `defaults write com.microsoft.OneDrive-mac EnableAddAccounts -bool True` into a terminal window and you will be able to log into a business account in OneDrive. (Apparently academic accounts are business accounts).

![Personal Account](Wrong)

This will allow you to log into the academic account and places another cloud on the menu bar.

![Personal Account](Academic)
