### Adding Light Rays <!-- {docsify-ignore} -->

!> Adding light rays is easy, all you have to do is to **drag and drop their prefab**. Unpack it only if you want to edit its hierarchy independently from the prefab.

?> I would also advise you to make your own light ray textures that will suit your game shape design, as it’s a quick
process that can incredibly boost your game looks.

![logo](images/18.png ':size=800')

#### - Light Ray component

?> Light Ray needs a Sprite Renderer with a compatible light-ray material and texture. It is a visual sprite effect; it does not emit URP 2D light.

?> **Dist Start Fade** is the camera distance at which the shader response starts changing. **Fade Length** is the distance used to interpolate the effect.

!> Keep Fade Length above zero and make sure the scene camera is tagged MainCamera.

?> Use the Sprite Renderer sorting layer and order to place the ray behind or in front of scene objects.

?> Every Light Ray owns a material instance at runtime. Avoid using a very large number of separate Light Ray components.
