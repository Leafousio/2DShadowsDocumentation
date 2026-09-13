### Adding Directional Shadows <!-- {docsify-ignore} -->

#### - Step 1 : URP

!>Currently, Modern 2D Shadows Shaders work only with the **Universal Render Pipeline** for 2D.

?>If you don’t know how to set it up, check out this 1 minute YouTube tutorial:

https://www.youtube.com/watch?v=pjpcitJim04 (UNITY 2020 LTS and lower)

https://www.youtube.com/watch?v=BCR2xQ7jWMU (UNITY 2021 LTS and higher)

#### - Step 2 : Texture settings

!> A readable sprite texture is required only when the caster uses **Auto** pivot detection. Auto scans the sprite pixels to find its bottom contact point.

?> If a texture cannot be made Read/Write enabled, select **Sprite** or **Custom** as the Pivot Source on Stylized Shadow Caster 2D.

![logo](images/1.png ':size=600')

#### - Step 3 : Sorting layer settings 

!> Create the sorting layer named in **Shadow Sorting Layer**. The default name is **Shadows**.

?> Modern 2D Shadows does not create or rename GameObject layers, sorting layers or tags, and does not edit ProjectSettings/TagManager.asset. A **Shadow tag** is not required. Generated shadows inherit the caster GameObject layer.

?> New shadows use the global Shadow Sorting Layer, unless the caster enables Override Sorting Layer.

#### - Step 4 : Player settings 

!> Make sure that your Color Space is set to Linear : 

![logo](images/3.png ':size=600')

#### - Step 5 : Adding Shadows

!> Now that we took care of technical things we need to setup, we can add our shadow system and directional shadows! 

?> System shadows(directional shadows) are rendered in real time, including things like: Direction, Floor angle, Ambient Color, Falloff, and more.
They are generally good for 2.5D games, with objects drawn in perspective.

![logo](images/4.png ':size=600')

!> Firstly, we must **add the 2D Stylized Lighting System to the scene** (it's in prefabs folder): 

?> You can unpack the prefab for a completely scene-local setup, or keep it as a prefab instance and save your changes as prefab overrides.

![logo](images/5.png ':size=600')

> Or create an empty gameobject and add 2D stylized lighting component :

![logo](images/setup.png ':size=200')

!> Now, **set the camera Transform**(in the  2D Stylized Lighting System settings) **to your camera**, or the parent that controlls it.

![logo](images/6.png ':size=600')

!> Now the only thing left is to **add stylized shadow casters to sprites which will cast shadows**.

![logo](images/7.png ':size=600')

?>  Now you should see your shadows!

?>  All there’s left is to tune them to your liking and make your game look better!

?> Use **Create / Repair All** on 2D Stylized Lighting if a scene was migrated from an older version or generated shadows need to be repaired.
