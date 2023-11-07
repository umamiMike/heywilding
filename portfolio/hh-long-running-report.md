---
author: "Mike Wilding"
date: "2022-02-14 01:21:53 PM"
title: "Server debugging and crash prevention"
description: "A walkthrough of a solution I implemented"
draft: false
tags:
- debug
categories:
  - write-up
  - Case Study
---

I troubleshot a crashing memory leak in the BEAM (erlang virtual machine) and implemented a robust solution.

### Long Running Reports Bugfix

Debugged a server problem and developed a solution to prevent a server crash during report generation.


#### Problem

An "admin" user might want to generate a csv report from the database. They could accidentally run a report that would cause a memory leak potientially causing the server to crash. It was also easy for a user to run the worst case scenario accidentally.

#### solution

- Used `:observer.start()` to track down the memory bloating process.
- converted from Enum.map to Stream.map, and the [zstream library](https://github.com/ananthakumaran/zstream)
- added cancellation process by way of storing the pid of the stream to the [ETS](https://elixir-lang.org/getting-started/mix-otp/ets.html), endpoint to handle the call, and UI to trigger cancellation


#### Technical Breakdown of Solution

- Investigated error
- process was using an Enum.map which was eager and could create a memory leak that could bring the **Erlang Virtual Machine**.
- Converted Enum to Stream process which is lazy loaded streaming process.
- added and used the [zstream library](https://github.com/ananthakumaran/zstream)
- With the memory problem fixed, I added a feature to allow the user to cancel the report
  - added using [ETS - The Elixir programming language](https://elixir-lang.org/getting-started/mix-otp/ets.html)
  - added api endpoint to handle the async cancellation
  - cancel the streaming process and remove the zip file.
