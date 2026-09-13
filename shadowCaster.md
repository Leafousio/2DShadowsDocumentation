### Stylized Shadow Caster 2D Component <!-- {docsify-ignore} -->

?> Add Stylized Shadow Caster 2D to a GameObject with a Sprite Renderer and an assigned sprite. The component creates and maintains its base shadow and the required per-light shadows.

#### - Shadow Pivot

?> **Pivot Offset X / Y** moves the contact point when the projected shadow does not meet the sprite correctly. **Flip Shadow X** corrects sprites whose visual direction is reversed.

?> Enable **Override Default Pivot** to choose a Pivot Source for this caster:

> **Auto** scans readable sprite pixels for the bottom contact point.

> **Sprite** uses the pivot imported in the Sprite Editor.

> **Custom** uses the assigned Custom Pivot Transform.

!> Auto requires Read/Write enabled on the sprite texture. Sprite and Custom work without pixel reading.

#### - Sorting

?> Enable **Override Sorting Layer** when this caster should not use the Lighting System Shadow Sorting Layer. Enter the name of an existing sorting layer.

?> Generated shadow GameObjects inherit the caster GameObject layer. The component never creates a new project layer or tag.

#### - Per-Caster Shadow Properties

?> Enable this section to override Ambient Color, Shadow Reflectiveness, Shadow Alpha, Shadow Narrowing and Shadow Falloff for one caster.

?> These values apply to the directional/base shadow and every generated per-light shadow for this caster.

#### - Animated and atlas sprites

?> The current Sprite Renderer sprite and texture are copied to generated shadows. Alpha clipping is preserved for animation frames and atlas sprites instead of rendering the sprite's tight mesh as a solid polygon.

#### - Generated Shadows

?> **Create** adds missing shadow objects. **Rebuild** replaces and recreates them. **Delete All** removes the base and all per-light shadows belonging to this caster.

?> Per-Light Pairs displays how many subscribed-light hierarchies currently belong to this caster.

!> Do not manually rename, reorder or edit generated shadow children. A later repair or rebuild can replace them.

#### - Runtime control

```csharp
StylizedShadowCaster2D caster = GetComponent<StylizedShadowCaster2D>();

caster.CreateShadow();
caster.RebuildShadow();
caster.DeleteAllGeneratedShadows();
```
