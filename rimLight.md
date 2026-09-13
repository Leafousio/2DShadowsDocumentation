### Adding Fake Rim-light   <!-- {docsify-ignore} -->

?>Sprites fake Rim Light Generator is a tool for adding colored gradients for each side of your sprite via shader.

?>It can be used to blend your sprite with surroundings, make it stand out/ fake local light and with many more
scenarios.

!> Add Sprite Gradients script to sprite gameobject : 

![logo](images/19.png ':size=600')

!> Set the 2D Stylized Lit Material

![logo](images/20.png ':size=600')

Now you can play with the values until it looks good.

#### - Sprite Gradients component

?> Assign the Sprite Renderer, or leave it empty so the component uses the Sprite Renderer on the same GameObject.

!> Assign a material that uses the **2DStylizedLit** shader. The component creates a per-object material instance so every sprite can have different gradient values.

?> **Gradient Top, Right, Left and Bottom** set the color coming from each side. Their Falloff values control how far each side reaches across the sprite.

?> **Bot Darken** and **Bot Transparency** adjust the lower part of the sprite. **Smoothness** controls the gradient transition.

?> Values update in Edit Mode. This is a fake rim-light/gradient effect and is independent from URP Light2D subscriptions.

!> Per-object material instances use more memory and reduce batching. Use this component only on sprites that need individual gradient settings.
