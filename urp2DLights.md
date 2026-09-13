### URP 2D Light Modes <!-- {docsify-ignore} -->

?> Modern 2D Shadows 2.2.7 creates one reusable shadow hierarchy for every active Stylized Shadow Caster 2D and subscribed URP Spot/Point Light2D pair.

!> The project must use the Universal Render Pipeline and a 2D Renderer supported by the exact Unity editor version.

#### - Choosing a mode

?> **directional_and_URP_2D_Lights** renders one normally customizable directional shadow plus one independent shadow for every subscribed supported light. **Directional Shadow Strength** controls only the base directional shadow.

?> **URP_2D_Lights_mode** renders only independent per-light shadows.

?> Existing scenes serialized with the old Unity2D Persistent and Unity2D Realistic enum names keep the same selected enum values after upgrading.

#### - Subscribing lights

?> **Add Scene Spot Lights** appends supported scene lights. **Replace From Scene** replaces the current list. **Clear** removes all subscriptions.

?> **Auto Subscribe Once** can populate an empty list when an older scene first enters a URP mode. It does not perform a scene-wide search every frame.

?> **Build / Repair All Per-Light Shadow Pairs** immediately creates or repairs the pairs. **Pair Build Budget** limits automatic pair creation per update to avoid a large frame spike.

!> Only Spot/Point Light2D is projected. Recent Unity Inspectors call it Spot, while C# uses `Light2D.LightType.Point`.

#### - Runtime lights

```csharp
LightingSystem.system.RegisterLight(spawnedLight2D);

// Call before pooling or destroying the light.
LightingSystem.system.UnregisterLight(spawnedLight2D);

// Optional scene scan. True appends to the current list.
LightingSystem.system.SubscribeAllSceneSpotLights(true);

LightingSystem.system.ClearSubscribedLights();
```

#### - Realistic rendered-light detection

?> **Persistent Shadow Alpha is off by default.** Every shadow fragment samples the four ShapeLight blend-style textures rendered by the URP 2D Renderer.

?> This uses the rendered light result at that screen position, including intensity and color, inner and outer radius, inner and outer Spot angle, falloff, blend styles and overlapping lights.

?> The CPU radius and cone checks are conservative visibility checks. The final realistic fade comes from the renderer light textures instead of a second duplicated distance fade.

!> URP exposes one ShapeLight texture for each blend style, not a public texture for every individual Light2D. Each pair still has its own projection direction, length, visibility and hierarchy, while realistic per-pixel alpha uses the final combined rendered light at that pixel.

#### - Persistent Shadow Alpha

?> Enable **Persistent Shadow Alpha** to keep the former distance-independent shadow alpha. This option is available in both URP modes.

?> The light enabled state, Spot cone, intensity threshold and optional GameObject-layer filter still apply, but radial distance and ShapeLight texture attenuation do not fade the shadow.

#### - Intensity and projection controls

?> **Use Intensity Presets** provides preset cutoffs and supported intensity ranges. Disable it to set Minimum Light Intensity and Full Shadow Intensity manually.

?> **Per-Light Shadow Strength** multiplies the shadow response. Shadow Distance Min / Max controls the distance range used for projection length. Length Multiplier Min / Max controls the shortest and longest projected shadow.

?> **Spot Direction Offset** corrects the cone direction only when a custom URP setup visually differs from the Light2D local +Y direction.

?> Enable **Filter Lights By GameObject Layer** and choose Allowed Light Layer when only lights on one GameObject layer should create pairs.

#### - Disabled and removed lights

?> A disabled light or a light rejected by the selected layer filter keeps its generated pair reusable, but its shadow renderer is disabled. Unregister pooled or destroyed lights so unused subscriptions can be cleaned up.

#### - Disable Shadow Blending

?> The bundled non-stacking material uses a stencil path. The Lighting System orders the strongest/darkest shadow candidate first so overlap selection is deterministic instead of depending on hierarchy traversal order.

!> Custom materials or render settings can change the result. This option should not be treated as an unlimited mathematical per-pixel maximum.

#### - Performance

?> Generated pairs share the selected shadow material and reuse Material Property Blocks. Properties update only when relevant settings, light data, alpha or sprite data changes, while transforms continue to follow moving casters and lights.

?> There is no per-frame scene-wide Light2D search. Subscribe only required lights and register runtime-created lights directly.

?> Realistic alpha samples up to four ShapeLight textures for each shadow fragment. Keep the number and screen size of overlapping per-light shadow sprites under control. Persistent Shadow Alpha is faster when realistic radial fading is not required.
