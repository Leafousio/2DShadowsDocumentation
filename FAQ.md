
### FAQ <!-- {docsify-ignore} -->

#### Why is no shadow created?

?> Make sure the scene has one active 2D Stylized Lighting component, Show Shadows is enabled, the caster has a Sprite Renderer with a sprite, and the named Shadow Sorting Layer already exists. Press **Create / Repair All** after migrating an old scene.

#### Why is the shadow a solid polygon instead of the sprite shape?

?> Update to Modern 2D Shadows 2.2.7 and rebuild the generated shadows. The current version explicitly keeps the Sprite Renderer texture in each generated property block, including animated and atlas sprites.

#### Why does a URP Light2D not create a shadow?

?> Only the Spot/Point Light2D shape is supported. The light must be subscribed, enabled, above the configured intensity threshold, inside its cone, and accepted by the optional GameObject-layer filter. The project also needs a URP 2D Renderer.

#### Why does the Inspector say Spot/Point?

?> Recent Unity Inspectors call this Light2D shape Spot, while the scripting enum is still `Light2D.LightType.Point`.

#### What is the difference between the two URP modes?

?> **directional_and_URP_2D_Lights** keeps one customizable directional shadow and adds one shadow for each subscribed URP light. **URP_2D_Lights_mode** renders only the subscribed per-light shadows.

#### What does Persistent Shadow Alpha do?

?> It is off by default. Off uses realistic per-pixel attenuation from the URP 2D Renderer light textures. On keeps the old distance-independent alpha while light enabled state, intensity threshold, cone and layer filters still apply.

#### Why are several shadow children generated below one caster?

?> The base/directional shadow and every subscribed supported light use independent reusable hierarchies. Do not rename or manually edit generated children because Create, Rebuild or Repair can replace them.

#### Does Disable Shadow Blending select the darkest shadow?

?> It prevents stacking through the bundled stencil path and deterministically draws the strongest/darkest candidate first. It should not be treated as an unlimited mathematical per-pixel maximum for every custom material or render configuration.

#### Why did unexpected GameObject layers appear?

?> Modern 2D Shadows 2.2.7 does not change ProjectSettings/TagManager.asset and does not create GameObject layers, sorting layers or tags. Generated shadows inherit the caster layer. If an older import already changed the project, restore TagManager.asset from version control or remove only the unused entries manually in Project Settings.

#### Do sprite textures need Read/Write enabled?

?> Only Auto pivot detection needs readable pixels. Select Sprite pivot or assign a Custom pivot when the source texture is not readable.

#### Which Unity versions are supported?

?> The package minimum is Unity 2022.3. It includes API guards for Unity 6.5, 6.6, 6.7 and subsequent Unity 6.x releases. Always test with the URP version supported by the exact Unity editor used for the project.
