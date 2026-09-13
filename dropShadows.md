### Generating Drop-down Shadows <!-- {docsify-ignore} -->

!> **before proceeding further, make sure your project uses URP and the required sorting layer already exists.**

Drop down shadows are perfect for sprites that don't work well with directional shadows.

It’s also important to note that they are generated objects and are not projected in real time like system shadows.

![logo](images/8.png ':size=600')

!>  First, we must put the Stylized Lighting System in the scene (detailed exlpanation in step 5 of "Adding Directional Shadows").

!>  Now, let’s add the Drop Shadow Generator to an object which we want to have a drop shadow.

![logo](images/9.png ':size=600')

#### - Drop Shadow Generator component

!> The GameObject must have a Sprite Renderer, and the scene must contain 2D Stylized Lighting with its Drop Shadow Material assigned.

?> Enable **Own Material Instance** only when this drop shadow needs material values different from every other drop shadow. A separate instance costs more memory and can reduce batching.

!> Press **GenerateDropShadow** to create the shadow child. Pressing it repeatedly creates additional children, so delete an old generated child before generating a replacement.

?> The generated Sprite Renderer uses the **Shadows** sorting-layer name by default. Modern 2D Shadows does not create that sorting layer; create it first or change the generated Sprite Renderer sorting layer manually.

?> The generated child copies the source sprite at generation time. Use Stylized Shadow Caster 2D when the shadow must follow live projection, animation and light changes.

![logo](images/10.png ':size=600')
