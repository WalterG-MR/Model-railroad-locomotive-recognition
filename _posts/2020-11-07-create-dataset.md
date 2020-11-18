--- 
layout: post
title: the dataset and what followed
date: 2020-11-07
---


To create a dataset of more than 1000 labeled images seem to be a very tedious thing at first.
But after thinking it over, the solution was quite simple : my program that runs the locs knew which loc passed the camera. I wrote this program myself ( used to be programmer ) in C# and i was able to add coding that pulled the picture from the raspberry, and label the file with the name of loc and a timestamp. So while working on my railroad ( there is always something to do ) i collected the images automatically for the dataset, paying attention to separate them in training and testing data.
Changing the speed of the locs and/or changing the light conditions i got a variation of the position and colors of the image.
I also eliminated the duplicates by calculating a hash code as described in the course.
Now i recalculate my model(s) now and then when i have a sufficient grow of image count.

The most interesting part was now to be tackled : recognizing the loc and display the name on a LED Panel ( 4 times 8 x 8 ) to let everyone know i was able to use DL4CV :slight_smile: :slight_smile: :slight_smile:

Before starting to use the % accuracy of my model, i reflected on how i wanted to define “accuracy”. Because just calculating the number of loc images that were recognized and compared to the total images did not seem correct to me. What if i took one loc that was recognized and send him 100 times passed the camera for a total of 120 images, would i then have 83% accuracy ? Of course not. Only 1 loc out of 21 was recognized.
So i define accuracy as being the number of locs recognized all the time, compared to the total number of locs. Locs being recognized only now and then do not add to the accuracy.

The first solution i tried was based on the ColorHistogram and i was sure that this would give me almost 100%. But to my great disappointment i only reached a poor 20%
I verified my model in running it over the training images, and it proved to be correct since i got 100% recognition as a result. But using the test images from the other camera did not perform well.

The second solution was using keras and the smallVGGnet as i read in one of the introduction lessons.
It performed better, but i did not got over 30% whatever i tried. Changing the data-augmentation parameters, reposition the camera to have the same angle and more.

In the course i reached 3.3.4 BOVW and i thought that would be the solution.
But it did not work at all for me, so i gave it up - probably too soon.

What worked ? I’ll present it in the next part. 

To end this part i've added a picture of how i follow up the results :
On the left is the current(new) picture of the reference spot
On the right is the current(new) picture of the to-be-recognized spot
n1(n2/n3 means n1 locs recognized all the time, n2 locs sometime NOT recognized, n3 total nbr of locs
