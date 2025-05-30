
# Journal For Computer Vision Task


## What I have gathered so far

Our second module task requires us to create a C++ program that utilizes our webcam. The objective, track an object based on a specific colour. At first it seems like a scary and difficult assignment but so far on what I'm reading it's not that bad.

## How the Program will work

So from my limited understanding of the topic, how it will work is based on image detection. So a video is basically just a bunch of pictures snapped at a highspeed and collectively produce a video (Crazy right? Motion picture). 

The program will track HSV (Hue, Saturation, and Value) -> type of matrix that stores pixel values for a computer to recognize color. Refer to previous notes but TLDR computers only look at matrices -> greyscale every Mat(i,j) each integer basically represents that intensity of the pixel from a 0-255 scale (black = 0 and white = 255). For BGR and HSV each pixel contains a tuple that stores the given values so its a little more complicated but still I understand (at a base level) what's going on. 

Now with what we just said -> I will input a range, as a colour is more of a spectrum than a definitive value. 

Each frame provided from the webcam will be scanned, pixel by pixel to see if the pixel is within the range, if it is than the program will take note of it. I'm assuming that the amount of pixels will need to be taken into consideration -> the more green pixels found in a condensed area will be taken into consideration.

**AFTER LATER INSPECTION TURNS OUT I AM RIGHT**

There's an OpenCV function 
```
c = max(contours, key = cv::contourArea)
```

This basically scans and keeps track of the max area created by a contour (not really sure what a contour is, I think it's just a blanket term for an undefined shape -> undefined meaning like its a shape but not a categorical shape like a circle or square).

So if we are tracking lets say green. If there is a green t-shirt versus a green water bottle, the green t-shirt (if its a larger object -> most likely unless really big water bottle) will be tracked due to this function. 

Possibly can create an if condition to create a threshold for the object (but this seems kinda hard cause I don't really know how each object will convert to pixels etc, so like we can work around this by just picking a colour that isn't common but the object I choose will be dominant). 

Now to show it's tracked, you can just use an OpenCV function to create a circle around the center of the object. Honestly I thought it was gonna be harder but the OpenCV library creates a lot of short cuts. If you had to manually do this from scratch it's kinda gg, but hey, it's a module that I can probably get done relatively quickly. The hardest part was understanding how images and stuff work, but I got through the basics pretty quickly (thanks to chatgpt obviously).

## Docker-Rancher-CMake

Honestly the hardest part of this will be setting up the environment, so far its been a pain to get everything set up. But honestly, it's a good lesson. I kinda just used chat to guide me through it. 

## Docker and Rancher

To be honest both of these I kinda just let chat run me through it, but I'll write some brief stuff on how docker works and what a docker image is.


## Docker

### Docker Image

the docker image is basically the blueprint, it has everything needed to run an app - code dependencies, environment variables and configuration files.

So a file that gives another user every dependency they need to install, pretty nice if you ask me. Kind of a pain to find every extension and dependency to download. I feel like theres gotta be more to it though.

So most of the time when I create applications, I need to make my own Docker Image - seems kind of lame but its needed to be able to create reusuable code (I think?). There are boiler plate dockerfiles for common applications like MySQL, but for custom apps that I create I need to create the Docker Image.


```

# Use Debian Bookworm as base

FROM debian:bookworm

# Install tools and dependencies

RUN apt-get update && apt-get install -y \

    git \

    build-essential \

    cmake \

    wget \

    unzip \

    pkg-config \

    libopencv-dev \

    libgtk2.0-dev \

    libavcodec-dev \

    libavformat-dev \

    libswscale-dev \

    libv4l-dev \

    libxvidcore-dev \

    libx264-dev \

    libjpeg-dev \

    libpng-dev \

    libtiff-dev \

    libtbbmalloc2 \

    libtbb-dev \

    libgl1-mesa-glx \

    && apt-get clean

  

# Set working directory inside container

WORKDIR /workspace

```

This is the DockerFile used for the computer vision project, the file 

## Rancher

Will talk about this more, sorta just like the kubernetes handeler -> I don't think I need to really know this 




