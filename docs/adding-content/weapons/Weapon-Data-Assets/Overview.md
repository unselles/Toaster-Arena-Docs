---
sidebar_position: 1
---

### Overview for weapon data assets

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
### Using shooting montages for weapon animation
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



### Settings > Shooting > Secondary > Double Shot
* **Can_double_shot:** Can this weapon shoot twice? (Used for double barell shotgun).
* **Double_recover_delay:** Time delay that this weapon will wait before being able to shoot again after double shooting (Shooting cooldown).



### Settings > Shooting > Secondary > Scope
* **DA_Scope:** Scope data asset that this weapon will use when aiming trough a scope.



### Settings > Shooting > Secondary > Aim
* **DA_Smart_Aim:** Aim data asset that this weapon will use when aiming.


### Settings > Shooting > Secondary
* **Secondary_mode:** Secondary actions that this weapon performs (Double shot, Reving, Aiming, Scoping, etc.



### Settings > Shooting > Spread
* **Spread_min:** Minimal spread of this weapon when shooting.
* **Spread_Max:** Maximun spread of this weapon when shooting.
* **Spread_to_add:** Ammount of spread to add per shot.
* **Spread_to_remove:** Ammount of spread to remove when not shooting.
* **SpreadBad?:** Makes it so that if the weapons is not zooming then spread will be all over the place .



### Settings > Shooting > Splash Damage
* **Splash_radious:** Radious in units for explosion damage (is also used to calculate damage falloff based on epicenter distance).
* **Splash_Particle:** Particle system used for splash damage.
* **Splash_SFX:** Sound effect used for explosion sounds.
* **Self_damage_multiplier:** Controls a resistance factor for shooting itself with splash damage or weapons damage (Used to prevent rocket jumping from instantly killing the player).



### Settings > Shooting > Rev
* **Rev_Ramp_rate:** Rate that this weapon will rev up (Smaller values will make the rev slower while big values will make it faster).
* **Rev_multiplication_Max:** Maximun Rev value of this gun (Used as a damage multiplicator).
* **Rev_multiplication_Min:** Minimun Rev value of this gun (Used as a damage multiplicator).
* **Rev_multiplication_curent:** Current Rev value of this gun (Used as a damage multiplicator and starting point).
* **Rev_start_delay:** How long will it take the weapon to start multiplying it's damage after it started reving.
* **Rev_end_delay:** How long will it take the weapon to stop multiplying it's damage after it stoped reving.



### Settings > Shooting > Melee
* **Meele_cast_extensions:** Trace extention of melee weapon hit trace (Leave as default).



### Settings > Shooting > Projectile
* **Projectile_class:** Projectile class that this weapon will (only avilable if the fire_mode is set to projectile).
* **Server_only_spawning?:** Makes it so that only the server spawns the projectile(Used for item throwables).
* **ProjectileBehaviour:** How will this projectile behaved when created.



### Settings > Shooting > Muzzle
* **ShootingParticle:** Shooting particle that this weapon will use.
* **MuzzleFlashLightColor:** Light color for the muzzleflash.
* **MuzzleFlashLightIntensity:** Light intensity for the muzzleflash.
* **Muzzle_socket:** Muzzle socket for this weapon (Light and particles will be attached to this socket).



### Settings > Shooting > Casings
* **DA_casings:** Data asset for bullet casings that tis weapon will use when casing ejection is trigered.



### Settings > Shooting > SFX
* **Shooting_SFX_Transience:** Transience sound effect for this weapon when shooting (Transience is a mid range sound).
* **Shooting_SFX_Mech:** Mechanical sound effect for this weapon when shooting (Mech is a close range sound and dinamically altered based on ammo count).
* **Shooting_SFX_Kick:** Kick sound effect for this weapon when shooting (Kick is a Close range sound and used to provide an extra kick for the weapon).
* **Shooting_SFX_Tail:** Tail sound effect for this weapon when shooting (Tail is a long range sound and can be heard from distance).



### Settings > Shooting
* **Fire_delay:** Delay in seconds that this weapon takes per shot.
* **Ray_lenght:** Hitscan ray length when shooting.
* **Ray_thickness:** Hitscan ray thickness when shooting (Used as an aid for the player when shooting) (Only used if CustomRayThickness is set to true).
* **Fire_mode:** Changes shooting behaviour (None = Nothing, Melee = Melee weapon behaviour, Single = Semi automatic, Auto = Fully Automatic (golden standard for all weapons), Burst = Burst fire (Currently non functional), Grenade = Grenade functionality ) Diferent modes use deferent animation setups and these relies on animation notifies to work.
* **Shot_type:** Changes what this weapons shotsm projectiles or hitscan.
* **Rays_to_shoot:** How many "pellets" this weapon will shot at once (Used for shotguns).
* **Self_damage_multiplier:** Skeletal mesh asset that this weapon will use.
* **Shoot_camera_shake:** Camera shake that plays when the player shoots the weapon.
* **TracerType:** Tracer asset used when for creating tracer effects and impact effects.
* **CharacterDeathEffect:** Animation that this character will play uppon death.
* **Hitnarker_colors:** A collection of hitmarker colors used for damage (Keep at default).
* **Shooting_consumes_ammo:** Does this weapon use ammo when shooting?.
* **Damage_self_on_shoot:** Damage the weapon owner when whooting the gun (Used under certain cases and mostly for technical setups such as a health injector that damages the player before healing them).
* **CustomRayThickness:** Will use custom values from Ray_Thickness instead of a predefined value.
* **HirmarkerOnDamage:** Show a hitmarker when damaging something (leave as default unless weapon is special or a consumamble).




* **Model:** Skeletal mesh asset that this weapon will use.
* **Model:** Skeletal mesh asset that this weapon will use.
* **Model:** Skeletal mesh asset that this weapon will use.
* **Model:** Skeletal mesh asset that this weapon will use.
* **Model:** Skeletal mesh asset that this weapon will use.
* **Model:** Skeletal mesh asset that this weapon will use.
* **Model:** Skeletal mesh asset that this weapon will use.
* **Model:** Skeletal mesh asset that this weapon will use.
* **Model:** Skeletal mesh asset that this weapon will use.




