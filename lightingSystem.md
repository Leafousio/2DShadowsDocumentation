### 2D Stylized Lighting Component <!-- {docsify-ignore} -->

?> Add **Light / 2D Stylized Lighting** to one GameObject in the scene. This component owns the shared shadow settings, light mode, subscriptions, materials and generated-shadow maintenance.

#### - Shadows

?> **Show Shadows** enables all system shadows. Ambient Color, Shadow Reflectiveness and Shadow Alpha control their appearance. Shadow Length, Narrowing, Falloff and Tilt control the projection.

?> **Shadow Sorting Layer** is the name assigned to generated Sprite Renderers. The sorting layer must already exist; the component does not create project layers or tags.

?> **Disable Shadow Blending** prevents shadows from becoming darker where generated shadows overlap. The strongest/darkest candidate is ordered first for deterministic stencil selection.

?> **Camera / Follow Transform** normally points to the main camera or to the parent that moves it. It is also used by the shadow update culling area.

#### - Blur

?> Enable Blur to soften the projected shadow. Sampling Area controls the number of samples, Blur Strength controls the amount, and Blur Direction controls the axes.

!> A high Sampling Area is expensive, especially when many large shadows are visible.

#### - Light Source

?> **Directional** creates one directional shadow for each caster. Use Directional Angle to rotate the light direction.

?> **Single Point** projects each caster away from one assigned Light Source Transform. Shadow Distance Min / Max and Length Multiplier Min / Max control its length.

?> **directional_and_URP_2D_Lights** creates one customizable directional shadow plus one independent shadow for each subscribed URP Spot/Point Light2D.

?> **URP_2D_Lights_mode** creates only the independent shadows for subscribed URP Spot/Point Light2D components.

?> **Render In URP 2D Light Only** can restrict the traditional Directional or Single Point shadow to rendered URP 2D light.

#### - Shadow Sprite Pivot / Flip-X

?> **Use Sprite Pivot By Default** uses each imported sprite pivot instead of scanning for a bottom pixel. Default Flip X changes the base orientation. Flip X By Projection Direction can reverse the generated sprite when the light crosses the caster.

#### - Advanced / Dependencies

?> This foldout contains the shared system and drop-shadow materials, culling colliders and pivot-correction groups. Keep the prefab defaults unless you are replacing a material or building a custom culling setup.

#### - Generated Shadows

?> **Create / Repair All** creates missing objects and repairs old generated hierarchies. **Update All** refreshes their current data. **Delete All** removes every system-generated shadow from registered casters.

!> Generated child objects are implementation data. Edit the Lighting System or Stylized Shadow Caster 2D components instead of editing those children manually.
