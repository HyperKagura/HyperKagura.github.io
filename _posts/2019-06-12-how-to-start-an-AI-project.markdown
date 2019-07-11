---
layout: post
title:  "How to start building AI"
date:   2019-06-12 21:00:00 +0300
categories: AI BirdDetector
description: "Firstly, sit on the sofa to harness the power of boredom"
#`jekyll serve`
# {% highlight ruby %}
# def print_hi(name)
#   puts "Hi, #{name}"
# end
# print_hi('Tom')
# #=> prints 'Hi, Tom' to STDOUT.
# {% endhighlight %}
# [Jekyll docs][link-here]
---

Greetings, stranger!

[Recently](/ai/birddetector/2019/05/11/Dont_be_afraid_to_seem_starange.html)
I was thinking about creating a BirdDetector AI and here is a brief
report about how the things are going. Hope it helps you to get a better
understanding what Data Scientists usually have to cope with.

Zero step in this case is to motivate yourself. And here is my trick: I try to
talk to my friends about how I am going to make my really awesome idea come true.
After a couple of weeks they come by asking "And how is your project going?".
Having nothing to answer I become really ashamed that I haven't written a
single line of code yet and finally start moving.

## Divide and conquer

Let's be honest: without cheaty google APIs building a videostream bird detector
is a complicated problem. So we should split it up into simpler tasks, which are:

* Classifying: is this a picture of a bird or not?
* Finding location of bird on a single \*.jpg image
* Breaking a videostream on a set of \*jpg images and building dynamic tracks of birds

Now, when all the problems seem familiar, I can concentrate on Classification task
and start an infinite loop of collect-train-check. Today, Let's focus on the
first part of it.

## Collect data

As I am building a simple yes/no classifier to answer "Is it a bird?" question,
what I need is a set of bird images and a set of non-bird pictures. By the way,
empty balcony would be ideal - it is actually a target non-bird. As for birds,
Google search wisely advised me to check out
[here](http://www.vision.caltech.edu/visipedia/CUB-200.html). Keeping in mind
that I will have to solve location task, I have decided to modify the set, so
each picture should:

* be square
* have a bird in the center
* bird should take as much space as it can (tails can be cropped)

Hopefully, when I will scan a big image with sliding window, I will have
"hits" at the true positions of birds.

Luckily I have a hobby of taking photos, therefore after spending about a week in
Adobe Lightroom I got a set of 500 square images. You can find it
[here](https://github.com/HyperKagura/BirdDetector/blob/master/README.md)

For non-bird pics I have decided to use some private photos from my albums and
iPhone, so I'll just tell you the following: you can pick up random images,
make sure there are no birds on it, and use Adobe Lightroom to crop squares
(left top corner, right top corner, center, etc.).

![Summer Carnaval, Kotor, Montenegro](/assets/images/posts/no_birds_in_dataset.jpg)
Just make sure there are NO BIRDS!
