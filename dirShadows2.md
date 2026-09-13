### Directional Shadows Features <!-- {docsify-ignore} -->

---

> <Font size = 4>You will find here main features of _2D Stylized Shadow System_, that may need a bit of explanation before working with them. </Font>

---

#### Shadow Update Culling

?>Shadow Update Culling makes the shadow properties updates apply only to shadows that are in viewport.
This speed-ups the system considerably.

?>Shadow Culling Colliders Should be generated automatically under the lighting system:

![logo](images/culling2.png 'size=400')

?> Colliders are generated based on your main camera size

![logo](images/culling3.png 'size=600')

!> For the culling system to work, you need to:

!> make the exit collider extends bigger that enter collider extends

!> exit and enter collider extends should be bigger than the main camera extends by the size of your biggest shadow in the scene

?>Now _2d stylized lighting_ system will use the OnTrigger2DEnter and Exit callbacks to add and remove shadows for updating. 

#### Shadow Pivot Corrections

?> In case that the stylized shadow caster is not perfectly centered and looks unnatural:

![logo](images/pivot00.png 'size=200')

?> You can correct the shadow pivot in the Pivot Corrections section of _2D Stylized Lighting_

![logo](images/pivot1.png 'size=200')

![logo](images/pivot2.png 'size=200')

?> Shadow should look better now

![logo](images/pivot0.png 'size=200')

?> In case you want to apply the same correction to multiple sprites, you can do it in Pivot Corrections Groups or Pivot Corrections Sprite Sheet Groups (if you're using sprites from spritesheet)

![logo](images/pivot3.png 'size=200')

#### 2D URP Light sources

?> You can use subscribed URP Spot/Point Light2D components as light sources. Every supported subscribed light gets an independent caster/shadow pair instead of blending the positions of the three closest lights.

?> Read **URP 2D Light Modes** for subscriptions, realistic rendered-light detection, Persistent Shadow Alpha and performance controls.

!> In C# the Spot shape is still named `Light2D.LightType.Point` by Unity.
