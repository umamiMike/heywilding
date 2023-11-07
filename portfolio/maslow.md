---
title: "Maslow, Web Client and Router Service"
description: "Tools to help you control your web habits written in Go and Javascript"
date: 2022-02-21T10:55:24-08:00
draft: false
tags:
  - React.js
  - Golang
weight: 1
---

### Maslow

#### Problem

Normally the domain of a sysadmin, We wanted to give a user control over their own browsing habits.  They should be able to choose which sites and how much access those sites have.


#### Solution

Created a prototype tool allowing a user to black-list or limit their access at
certain times. Useful for limiting problem internet habits or behaviors.

It consists of a golang authored binary running on a DD-WRT router which read
and wrote dnsmasq logs and leases and a react client to allow a user to
administer the rules for limiting their internet habits.

<!--more-->

### Technical Notes

- The administration service, built in **React.js** allows a user to manage
  devices and urls
- The **go** service, living on **a DD-WRT** enabled router, utilizes the date
  to create appropriate iptables rulesets.
- They are connected via **firebase**, acting as the datastore.

The idea here is that someone on your network says, "I'd like to use the
Internet for a while." and you, as their friend say, "Cool, I know you've done
your work and have gotten lots of exercise today, so go ahead and use it for
half an hour!"

Then you pull out your smartphone, navigate to a web address you have
bookmarked (or possibly open an app), find your friend's device in the list,
and tap "grant permission."

- Your friend now has open access for that amount of time

- Should your friend want more access after their time is up, they have to ask
  you again

- It makes sure that you all understand how much time is being used and that
  they are spending their time wisely.

