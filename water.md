### Adding Water <!-- {docsify-ignore} -->

!> **before proceeding further, make sure you did 4 first steps in "Adding Directional Shadows"!!!**

Fake water is a useful tool for nice natural environments, but it’s situational and can take a lot of attention from other
important elements, so use it with caution.

First, why do I call it fake?
It’s because this water doesn’t reflect objects and has a lot of limitations. It copies the camera render texture and
projects it with an offset, then its ads a ton of effect to give a feeling of “real” water.

#### First add a Water Camera prefab and assign those settings  : <!-- {docsify-ignore} -->


!>   Match its size to your main camera size 

!>   Create a Water layer and exclude it from rendering : 

![logo](images/11.png ':size=600')

!>   Take a render texture and assign in to the water camera output :

![logo](images/12.png ':size=400')

![logo](images/13.png ':size=400')

![logo](images/14.png ':size=400')

!> add the pool of water from prefabs and set its layer to “Water”

![logo](images/15.png ':size=600')

![logo](images/16.png ':size=600')