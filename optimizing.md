### Optimizing <!-- {docsify-ignore} -->

#### Directional Shadows <!-- {docsify-ignore} -->

?> keep the number of sprites with directional shadows under 1000

?> don't use blur, or keep the sampling area low 

?> avoid per-shadow properties

#### Water <!-- {docsify-ignore} -->

?> reduce the size of water Render Texture

#### Cloud Shadows <!-- {docsify-ignore} -->

?> types of clouds are ordered by their complexity, so _gradient noise_ clouds will be most preformant, while _Brownian On Gradient Noise_ will be the most expensive