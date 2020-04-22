---
title: "Pinhole Camera"
date: 2020-01-13T19:29:08+02:00
---


#### Pinhole diameter

> d = 2 * sqrt( F*λ )

* F = focal length, distance from pinhole to paper/film
* d = diameter
* λ = wavelength of light
* 550nm is good for black and white
* optimally less than 1/100 of focal length
* vingetting when diameter is near the thickness of material

#### f-number

>f-number = (distance to film/paper) / (pinhole diameter)

#### Exposure time

measure with something lets say that we get **1/60** with **f22**


let's calculate with pihole f-number 100

* light sensitivity change = (target f / measured f)²
* ex (100/22)² = **20.66**

exposure time is then **1/60 * 20.66 = 0.344** seconds

but remember we probably can't measure with as low ISO as the paper

which probably is between 2 and 10, so we have to count the steps and adjust accordingly 

| ISO|  |  | speeds| | |
|--|--|--|--|--|--|
|3|6|12|25|50|100|
|200|400|800|1600|3200|6400|

#### Reciprocity
At least with ILFORD papers, there is minimal need for longer exposure due to reciprocitation

[ILFORD Paper FAQ](https://www.ilfordphoto.com/faqs/photographic-paper-faqs/)

> For our papers - provided the exposures are within say a couple of hours, there is no real adjustment you'd need to make to whatever your initial metered reading is telling you to expose to.

https://github.com/ehagan/pinhole-camera-exposure-time

#### 35mm equivalent focal length
 Diagonal of 'normal' 35mm film is 43.3mm, 36mm wide and 24mm tall 

|image size | diagonal| width|
|--|--|--|
|4:3 width |	34.6 f/w |	36 f/w|
|4:3 diagonal |	43.3 f/d |	45 f/d|
|3:2 width |	36 f/w |	36 f/w|
|3:2 diagonal |	43.3 f/d |	43.3 f/d|
 (Table from [Wikipedia](https://en.wikipedia.org/wiki/35_mm_equivalent_focal_length#Conversions))

For a **5x7** paper (diagonal 218.7mm) and a true focal length of **100mm** we'll get the following

**43.3 100/218.7 = 19.8**

or with a **4x6** paper diagonal (127.6mm)

**43.3 100/127.6 = 33**

#### Sources
* [Wikipedia](https://en.wikipedia.org/wiki/Pinhole_camera)
* [ILFORD MULTIGRADE RC](https://www.ilfordphoto.com/multigrade-iv-rc-deluxe-glossy-sheets)
* [ILFORD MULTIGRADE FB CLASSIC](https://www.ilfordphoto.com/multigrade-fb-classic-glossy-sheets)

{{%attachments title="ILFORD Technical data" %}}
