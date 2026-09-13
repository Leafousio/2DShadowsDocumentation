### Optimizing <!-- {docsify-ignore} -->

#### Directional Shadows <!-- {docsify-ignore} -->

?> Use the enter and exit culling colliders so off-screen casters are not updated. Make the exit collider larger than the enter collider and include the longest possible shadow.

?> don't use blur, or keep the sampling area low 

?> Per-caster properties use a Material Property Block and do not need a unique shadow material, but changing large numbers of properties every frame still has a cost.

#### URP 2D Light Shadows <!-- {docsify-ignore} -->

?> Every subscribed supported light creates one reusable pair for every caster. Subscribe only lights that should cast projected shadows.

?> Use **Pair Build Budget** to spread creation across frames. Use **Build / Repair All Per-Light Shadow Pairs** only when an immediate editor rebuild is required.

?> Register and unregister runtime-created lights directly. The per-frame update does not search the whole scene for Light2D components.

?> Realistic URP modes sample the four URP ShapeLight textures for each shadow fragment. Avoid many large overlapping shadow sprites. **Persistent Shadow Alpha** avoids those texture samples but does not provide realistic radial fading.

?> Keep the light GameObject-layer filter enabled when only one layer contains shadow-producing lights.

?> **Disable Shadow Blending** uses the stencil-based non-stacking path. It orders the strongest/darkest candidate first so the result does not depend on hierarchy traversal order.

#### Water <!-- {docsify-ignore} -->

?> reduce the size of water Render Texture

#### Cloud Shadows <!-- {docsify-ignore} -->

?> types of clouds are ordered by their complexity, so _gradient noise_ clouds will be most preformant, while _Brownian On Gradient Noise_ will be the most expensive

#### Sprite Effects <!-- {docsify-ignore} -->

?> Light Ray and Sprite Gradients create material instances. Use them selectively when many identical sprites could otherwise share one material.
