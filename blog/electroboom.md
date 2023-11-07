---
author: "Mike Wilding"
date: "2022-04-06 19:46:06"
categories:
tags:
title: "A way  to Prioritize things I learned from Electroboom"
description: "I break down a video by Electroboom to learn a valuable way of comparing things"
draft: false
featured_image: images/medhi.png 
---
                 
I ran across [this video](https://youtu.be/nycAujdp708) where Mehdi from [ElectroBOOM](https://www.youtube.com/c/Electroboom/videos) was evaluating light bulbs of different types.

In performing his comparison he touched upon a something I find very important.  A methodology to compare a bunch of options.  I have found that without a way to do this it can be easy to get paralyzed by all the many choices you have.

{{< blog-image "IMG_20220313_090622_HDR.jpg" >}}

This is a simplification of the table he was drawing up while comparing the light bulbs.

|     good or bad     | property to evaluate  | incandenscent | halogen | cfl  | led  |
| :-----------------: | :-------------------: | :-----------: | :-----: | :--: | :--: |
| b1 (more is worse)  |  power usage (watts)  |      60       |   43    |  13  | 8.8  |
| g1 (more is better) | output level (lumens) |      700      |   750   | 850  | 800  |
| g2 (more is better) |     light quality     |       1       |    1    | 0.5  | 0.9  |
| b2 (more is worse)  |         life of bulb         |      2kh      |   1kh   | 10kh | 15kh |

In the subsequent columns the top row was the things he was comparing

### The good or bad column

- In the case of power usage, we want the light to use LESS power, so if the power consumption of the bulb is more, we think that is a BAD thing. so we label it with a prefix **b**

- in the case of the output level, we want it to give off MORE light so incadescent putting off 700 lumens is something we want, more is better, so we prefix it with a **g**

### The Magic of Math or _Deriving a useful value from the whole thing_


In this screenshot he is showing you an equation which adds up to a the **Consumer Experience Factor**



{{< blog-image "Algorithm for decision.jpg" >}}

<br>
<br>

#### How to do it in a nutshell:

1. make a list of options you want to compare
2. make a list of all the properties for each option
3. classify each property as "desirable" or "undesirable" 
4. measure each of the properties for all the options
5. for each option:
    1. multiply the "desirables" together
    1. multiply the "undesirables" together
    1. divide the positive value by the negative value
    1. this will yield the **Consumer Experience Factor** he mentions
6. Compare the numbers for each option. The higher the number the better.


The magic is that by **multiplying** the values in step 5, you dont have worry about the fact that one property might be  in **miles-per-hour** or **lumens** or **color**
