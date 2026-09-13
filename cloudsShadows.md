### Adding Cloud Shadows <!-- {docsify-ignore} -->

!> Add Cloud Shadows System to an empty GameObject with a Sprite Renderer.

![logo](images/17.png ':size=600')

?> Set the Sprite Renderer sorting layer above the ground and below objects that should appear in front of the cloud shadows.

#### - Cloud Shadows System component

?> **Cloud Type** selects Gradient Noise, Brownian Noise, Worley Noise or Brownian On Gradient Noise. The types are ordered from the lighter Gradient Noise option to the more expensive combined Brownian option.

?> **Camera Settings** use Main Camera by default. Enable Override Main Camera and assign Override Cam when the effect should follow a different orthographic camera.

?> **Visual Settings** control texture tiling, scale, Brownian transformation, alpha, maximum output alpha, shadow color, sun direction and alpha smoothing.

?> **Speed Settings** control displacement, speed and direction for both scrolling noise layers.

!> Only one active Cloud Shadows System should be used. The component is a singleton and removes duplicate components.

!> A camera is required. The system follows the selected camera and resizes its Sprite Renderer to cover the orthographic view.
