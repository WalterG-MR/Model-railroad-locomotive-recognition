---

title: "first images"

date: 2020-11-06

---


This is one of the approx 500 images i made of the 25 locs that are running ( but not all at the same time ) on my railroad project.

Before this image was to my satisfaction, a lot of painful trial and errors passed.

Considerations at the beginning :
Aim : a inexpensive solution to recognize a loc passing at a certain spot

Since i was familiar with the Raspberry Pi and adding a standard Pi-camera is not expensive, the
hardware was chosen.

I placed 2 independent sets at different spots on my railroad. One for taking the images to be trained and one for the images to be recognized.

Since on a model-railroad ( 1:87 H0 for experts :wink: ) there is not much space, i was forced to use the front of the loc. That was a limitation.
To make it possible to do this in daylight aswell as during the “night” i selected the spots in a tunnel and add LED light to it ( Luxeon 1W )
To make the images comparable i fixed the camera settings as described in Chapter 6 of Raspberry Pi for CV and on the internet pages of picamera
To make sure that the camera took the picture at the right moment, i added 2 Infra Red switches : 1 for the LEDS to switch on, and 1 for the camera

I decided against video stream after having played with it, since i could not get it to work stable enough. (At that time i was using Raspberry Pi 3 )

The setup finished, it was the time to start working on Deep Learning.
After the Module 2 of the Guru course about Object Detector - and a lot of restarts from the beginning - i managed to create a very good Object Detector with Dlib and the image annotation tool ImgLab. Even adding locs that the Object Detected never saw, it detects almost perfectly the loc in the image.
Trying to use other ways to identify the position of the loc failed for different reasons. I use locs from Belgium, Germany, Switzerland and a US Loc ( Alco PA-1 ) having different profiles, colors, etc. So i never succeeded in finding contours in a reliable way using other methods than ImgLab.

Now that i am able to find the ROI in the image i can transform it to the way i wanted it

Take a 480 x 320 image using a fixed environment
determine a 100 x 80 ROI ,
resize it to 96 x 96 to be able to use smallVGGNet as i learned in one of the introduction lessons
Now i needed a dataset … which i will describe tomorrow :upside_down_face:
