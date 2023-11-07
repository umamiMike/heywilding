---
author: "Mike Wilding"
date: "2022-02-14 03:45:07 PM"
title: "Activity Log migration"
description: "Using go to fix PHP and a design issue for a moving ship"
draft: false
weight: 15
---

## Activity Logger

Implemented a seperate service to allow a bloated user activity-log to be shunted to a seperate database via yml configuration.
Work consisted of creating a concurrent Golang service with config for systemd and a new server side **PHP** client to write out the data.


**HIPAA** required a full user activity log. Data was stored in same **MySQL** db as the functioning app.
As the application grew the size of the log made the db bloated and much less manageable.

- Designed solution with project lead.
- Implemented a separate Go service as a binary executable to listen on a
- secure endpoint and write the activty data out to a seperate,
- runtime configurable database connection.
