### Adding Directional Shadows <!-- {docsify-ignore} -->

#### - Step 1 : URP

!>Currently, Modern 2D Shadows Shaders work only with the **Universal Render Pipeline** for 2D.

?>If you don’t know how to set it up, check out this 1 minute YouTube tutorial:

https://www.youtube.com/watch?v=pjpcitJim04 (UNITY 2020 LTS and lower)

https://www.youtube.com/watch?v=BCR2xQ7jWMU (UNITY 2021 LTS and higher)

#### - Step 2 : Texture settings

!> To create System Shadows, you must **make sprite textures** used as shadow casters **readable** :

![logo](images/1.png ':size=600')

#### - Step 3 : Layers and tags settings 

!> Create a **Shadow tag** for shadow casters, and **Shadows sorting layer** : 

![logo](images/2.png ':size=600')

?> New shadows will be placed on Shadows sorting layer, but you can configure the shadow sorting layer in Stylized Shadow Caster 2D options.

#### - Step 4 : Player settings 

!> Make sure that your Color Space is set to Linear : 

![logo](images/3.png ':size=600')

#### - Step 5 : Adding Shadows

!> Now that we took care of technical things we need to setup, we can add our shadow system and directional shadows! 

?> System shadows(directional shadows) are rendered in real time, including things like: Direction, Floor angle, Ambient Color, Falloff, and more.
They are generally good for 2.5D games, with objects drawn in perspective.

![logo](images/4.png ':size=600')

!> Firstly, we must **add the 2D Stylized Lighting System to the scene** (it's in prefabs folder): 

![logo](images/5.png ':size=600')

!> Now, **set the camera Transform**(in the  2D Stylized Lighting System settings) **to your camera**, or the parent that controlls it.

!> You also need to **unpack the prefab**, since any changes made to a prefab won't be saved!!!

![logo](images/6.png ':size=600')

!> Now the only thing left is to **add stylized shadow casters to sprites which will cast shadows**.

![logo](images/7.png ':size=600')

?>  Now you should see your shadows!

?>  All there’s left is to tune them to your liking and make your game look better!