---
layout: post
title:  "First BirdDetector is ready!"
date:   2019-06-12 21:00:00 +0300
categories: AI BirdDetector
description: "Breaking news: it is actually working"
---

Hello, all the curious creatures!

After [collecting some data](/ai/birddetector/2019/06/12/how-to-start-an-AI-project.html)
I decided to take a small pause to check out this amazing
[course on Tensorflow](https://www.coursera.org/specializations/tensorflow-in-practice?)!
If you want to have a quick start on Image Recognition or Natural Language Processing,
check this out!

But let's go back to out birdies.

An important factor to consider in my case is speed of recognition. To cope with
a video my program would have to process at least 5 frames each second and
on each frame about 20 squares will be scanned (but the more - the better).
In total I have to classify about 100 images per second. As you can see, the
recognition algorithm should be optimal.

At first, I was thinking about implementing usual SVM with
[HOG](https://www.learnopencv.com/histogram-of-oriented-gradients/) (flat-but-fast)
based on 128x128px instead of 64x128px for pedestrian recognition. But unlike standing
people birds can vary highly in spices and poses, therefore gradients might not build
a clear group. But I will test it one day...

So, my growing interest over Neural Networks whispered to my ear: "Try Convolutions".
And I just did it. I have to say the results have exceeded all the expectations.
2 hours of training gave me a 91% accurate system!

![Sad Birdie-Dog Noises](/assets/images/posts/sad_noises.JPG)

I have also organized a [Turing Test](https://en.wikipedia.org/wiki/Turing_test),
and the machine was just as good as people. Check this out!

![Lama-Swan](/assets/images/posts/lama-swan.JPG) ![Dogie-Bird](/assets/images/posts/dogie-bird.JPG)
