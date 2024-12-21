---
sidebar_position: 1
---

# Overview for weapon data assets

:::caution
This is a highly complex system with a lot of atributes, all the values should be documented here. But if some are missing, descriptions can be found at the `Data Asset` variables.
:::

:::caution
Weapons on TA are fully data oriented and not actor based, this means that we cant code in custom behaviour for them unless we use an intermediate object such as the `Debuff System`.
:::

The first step is to create a `Data Asset` that provides the game with enough information regarding a weapon.

Follow these steps:

1. Navigate to the appropriate folder in your Unreal Engine project.
2. Create a new `Data Asset`.
3. Select the appropriate parent class for the `Data Asset` this should be `PDA_WPN_Usable`.

Once the Data Asset is created, you can configure the following properties:

### Animations
These are a combination of animation montages used for character animation and aniamtion sequences for weapons

:::caution
Character animation must be strictly animation montages while weapon animations need to be animation sequences, however there is one exception to this rule with shooting animations
:::
## Using shooting montages for weapon animation
* **Anim_Shoot_Weapon_Montage** This variable will allow the weapon to play a shooting montage with blending and is mostly reserved for akimbo weapon setups
:::caution
Using "Anim_Shoot_Weapon_Montage" is driven from "Anim_Shoot_Weapon_M" as such both need to share the same indexes for animations.

Using animation montages also requieres that the weapon has it's own animation blueprint. The reference variable can be set at `Animations > Systems > AnimInstance`
:::

### Settings > Info > Icons
* **Show_icons:** This Weapon will show objective icons on the player that has the weapon equiped.
* **Icon_Ally:** Icon that will be visible to ally players of whoever holds this weapon.
* **Icon_Neutral:** Icon that will be visible to neutral players of whoever holds this weapon.
* **Icon_Enemy:** Icon that will be visible to enemy players of whoever holds this weapon.


### Settings > Info
* **Thumbnail:** 2D texture icon that will be used on UI elements for this weapon.
* **Crosshair:** Crosshair image that will be used for this weapon.
* **Model:** Skeletal mesh asset that this weapon will use.
* **Default_material:** Default material for this weapon Will use asset default if none.
* **DefaultMaterialSlot:** Material index that the default material will be applied to.
* **Socket_equip:** Character socket that this weapon will be attached to when equiped.
* **Socket_holster:** Character socket that this weapon will be attached to when Holstered (Not used as of now but it is considered for proxy weapons).
* **Weapon name:** Name for this weapon.
* **Weapon_description:** Description for this weapon.
* **Equip_delay:** Time in seconds that will take this weapon to be ready to shoot after being equiped.
* **AutoReloadLastShot?:** Weapon will automatically reload after shooting it's last round or atleast attempt to, should be active for all weapons unless it's a tool.
* **Hide_crosshair:** Hide crosshair when equipped.
* **Can_reload_in_tp:** Not used but it prevents the weapon from reloading in third person perspective (should be left as default).
* **Dot_crosshair:** Show dot crosshair for this weapon (Used for high acuracy guns that are challenging to aim such as the revolver).
* **Reload_can_happen_in_thirdperson:** Not used but it allows the weapon from reloading in third person perspective (should be left as default).
* **Hand_usage:** Prevents the hand from being used in certain animations Example (Preventing swim motion on the left hand for two handed weapons).
* **Show_ammo_counter:** Shows the ammo counter for this weapon (should be disabled for tools).
* **Hide_mags_counter:** Hides the mag counter for this weapon (should be disabled for tools).
* **DestroyOnHolster:** Unequips the weapon when holstered removing it from the player inventory (Used for objective weapons such as flags).
* **HideIfEmpty:** Hides the weapon and changes grabbing animations if the weapon runs out of ammo.
* **Show_description:** Shows the description for the weapon on the player hud (Useful for tools or weapons that have custom events like the fishing rod).
* **Use_constant_row:** Will use specified row when equiped (No longer used leave as default).




