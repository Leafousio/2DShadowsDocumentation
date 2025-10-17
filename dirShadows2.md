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

?> You can use 2D URP Lights as your light source

?> In case of multiple light sources near one shadow, shadow position will be interpolated between three closest light sources

![logo](images/ls.png 'size=200')

> **Minimum alpha** is the alpha of the shadow when it's not lit by the light source. It's adviced to leave it on 0 for realistic effect.

> Increasing **Strength in light** makes the shadow more visible even in weaker lights:

> **shadow distance min max** controlls minimum and maximum distance from light source that changes the shadow length

> **shadow length multiplayer** controlls minimum and maximum shadow length. Shadow length is minimal at the minimum distance to light source and maximal at the maximal distance to light source.

?> To see the example of this feature, open the _Point Lights_ demo scene:

![logo](images/ls2.png 'size=200')