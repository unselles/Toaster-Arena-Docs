---
sidebar_position: 1
---

# Weapon Data Assets

:::caution
This is a highly complex system with a lot of attributes, all the values should be documented here. But if some are missing, descriptions can be found at the `Data Asset` variables.

Weapons are fully data oriented and not 'actor' based, this means that we can't code in custom behaviours unless we use an intermediate object such as the `Debuff System`.
:::

The first step is to create a `Data Asset` that provides the game with enough information regarding a weapon.

Follow these steps:

1. Navigate to the appropriate folder in your Unreal Engine project.
2. Create a new `Data Asset`.
3. Select the appropriate parent class for the `Data Asset` this should be `PDA_WPN_Usable`.

Once the Data Asset is created, you can configure the following properties:

### Animations
These are a combination of animation montages used for character animation and aniamtion sequences for weapons

:::danger
Character animation must be strictly animation montages while weapon animations need to be animation sequences, however there is one exception to this rule with shooting animations
:::
### Using shooting montages for weapon animation
* **Anim_Shoot_Weapon_Montage** This variable will allow the weapon to play a shooting montage with blending and is mostly reserved for akimbo weapon setups
:::info
Using "Anim_Shoot_Weapon_Montage" is driven from "Anim_Shoot_Weapon_M" as such both need to share the same indexes for animations.

Using animation montages also requieres that the weapon has it's own animation blueprint. The reference variable can be set at `Animations > Systems > AnimInstance`
:::




### Animations > Systems 
* **AnimInstance:** Animation blueprint that this weapon will use (Only for akimbo setups).
* **RecoilAnimation:** Recoil Animation used for TP (-1=None, 0=Light, 1=Medium, 2=Heavy).



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



### Settings > Shooting > Projectile > Buildables
* **MaxBuildables:** Max allowed buildables.
* **BuildableClass:** Used for player made buildables like sentries or barricades.



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



### Settings > Shooting > Vehicle
* **UsePhysicalFireDirection:** Instead of using camera related traces, this weapon will use math to combine camera and barell traces to ensure that the weapon can be fired from barells while matching camera rotations.
* **VehicleWeaponRotationSpeed:** Simulated rotational speed of this vehicle weapon (The physical cannon of vehicles will use this to drive the animation) (Smaller values = Faster).
* **VehicleWeaponMaxPitch:** Maximun pitch rotation of this weapon (How up can this cannon look to).
* **VehicleWeaponMinPitch:** Minimun pitch rotation of this weapon (How down can this cannon look to).



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
*



### Settings > Reloading > Pump
* **Pump_Reloads:** Makes the weapon use a pump animation when a reload finishes (This pump is smart).



### Settings > Reloading > Mag
* **DA_Mag:** Physics mag data asset that this weapon will use.



### Settings > Reloading
* **Reload_type:** How this weapon reloads ( Mag= single mag reload, per bullet = Used for shotguns (needs to use propper animation setup) Energy = Weapon reloads automatically after a preiod of time (used for plasma weapons) Skip animation = weapon skips the reload sequence and instant reloads).
* **Reload_notify:** Reload happens on animation event intead of animation end (Used for weapons that you want to have the ammo count change instead of waiting for the animation to finish Ex, placing a mag should update the ammo counter (Notify driven).
* **Reloading_hand:** Hand that reloads this weapon, it will disable ik on the hand when weapon reloads.



### Settings > Damage
* **DamageMultOnShields:** If enabled damage multiplers will affect if player has shields (Used for AT sniper headshots that instantly kill players).
* **DamageBase:** Base damage of this gun.
* **ShotsToKillNoShields:** How many hits it takes the gun to perform base damage from up close based on range values (also used for damage falloff and splashdamage).
* **ShotsToKillNoShieldsMin:** How many hits it takes the gun to perform base damage from far away based on range values (also used for damage falloff and splashdamage).
* **ShotsToKillShields:** How many hits it takes the gun to perform base shield damage from up close based on range values (also used for damage falloff and splashdamage).
* **ShotsToKillShieldsMin:** How many hits it takes the gun to perform base shield damage from far away based on range values (also used for damage falloff and splashdamage).
* **Damage_multipliers:** Used to provide damage multiplication based on hitboxes (Headshots dealing double damage for some weapons).
* **Damage_multiplierNames:** Used in combination with damage multipliers variable.
* **Gore?:** Does this weapon dismember characters when killing?.
* **ExplodeLimbs?:** Will this weapon explode characters in to pieces when killing?.



### Settings > Bullets
* **Bullets-current:** Starting bullets of the weapon.
* **Bullets-max:** Max bullet count of the weapon.



### Settings > Mags
* **Mags-current:** Starting ammount of reserve ammo for the weapon.
* **Mags-max:** Max ammount of reserve ammo for the weapon.



### Settings > Inventory > Multiplayer
* **Weapon_collum_MP:** Slot collum used for this weapon.
* **Weapon_row_MP:** Slot row used for this weapon.



### Settings > Inventory > Singleplayer
* **Weapon_collum_SP:** Slot collum used for this weapon.
* **Weapon_row_SP:** Slot row used for this weapon.



### Settings > Inventory
* **MultiplayerWeapon?:** Does this weapon use the multiplayer slots or the singleplayer slots?.



### Settings > Falloff
* **Damage_falloff:** Will the damage of this weapon be reduced by range.
* **Reverse_fall_off:** Is the damage falloff reversed for this weapon? This means that the further the weapon is from a tarquet, the more damage it does.
* **Reverse_fall_off_range:** How far does this weapon need to be on maximun damage range.
* **Falloff_MaxLength:** Max distance length for calculation falloff damage Longer distances is less damage.



### Settings > AI > Hearing
* **CanAIHear?:** Can AI characters hear this weapon shoot?.
* **ShootingMaxRange:** Maximun range that the AI will be allowed to be distanced from to be able to hear the weapon shoot.
* **ShootingLoudness:** Loudness value for the gun (used to multiply by the max range.



### Settings > AI > Squad
* **Squad_CQCScore:** Factor that determines how likeley the AI will use this weapon on close quarters combat (Singleplayer only).
* **Squad_LongRangeScore:** Factor that determines how likeley the AI will use this weapon on Long range combat (Singleplayer only).
* **Squad_SupressionScore:** Factor that determines how likeley the AI will use this weapon on supression(Singleplayer only).



### Settings > Physics
* **Backwards_push:** Force to apply the player while airbone and shooting (Double barrell shotgun jumping).
* **Physics_impulse:** How much fore to apply to ragdolls or physics objects on hit.
* **Rocket_jumping_force:** Force to apply for rocket jumping physics.



### Settings > Overheat
* **Ammount_to_vent:** How much heat does this weapon vent per delay.
* **Vent_speed:** Delay based how much in seconds it takes to delay one digit of heat.
* **Vent_start_delay:** Delay for how long it takes this weapon to start venting heat.




### Settings > Fixes
:::info
Weapon fixes and offset tweaks can now be made entirely in engine by using the weapon offset tool that can be found at `Pause menu> Remote admin > Game CMD > Weapon offset tool`
:::



### Settings > Debuff
* **List of Active buff's or debuff's:** Character debuffs that this weapon applies when equiped at the player hands.
* **List of Pasive buff's or debuff's:** Character debuffs that this weapon applies when on the player inventory.* 
* **Buff's to apply on enemy:** Character debuffs that will be applied to characters that recieve damage from the weapon that arent on the player's team (Fire Damage).
* **Buff's to apply on ally:** Character debuffs that will be applied to characters that recieve damage from the weapon that are on the player's team (Healing buff from heal cannon).
* **BuffsToRemoveFromAlly:** Character debuffs that will be removed to characters that recieve damage from the weapon that are on the player's team (Fire extinguisher to allies).



### Settings > IK
* **Arm_IK:** Arm Ik chains that this weapon affects .
* **LeftIkSocket:** Hand socket that the IK will be used from (deprecated).
* **RightIkSocket:** Hand socket that the IK will be used from (deprecated).
* **UseOldIKMethod:** Uses old Ik method where the character hands are driven by weapon IK bones (Deprecated and should not be used).
* **LeftHandWeapon2IK:** Makes the left hand use ik from the weapon bone 2, usefull for dualweild or one handed melee weapons.
* **NonIKPlayAnims:** Makes non IK hands play weapon animations (Usefull for melee weapons that only use one hand.
* **Force_FabrIK_TP:** Forces IK to use FABRIK instead of poles (Usefull for melee weapons).
* **NonIkLocomotion:** Makes non IK weapons run locomotion (used for weapons that are one handed and have the other hand do something else like a moving animation).



### Settings > TP
* **TPHoldMode:** Pose for the character for holding this weapon, this affects pitch and yaw transforms (Entierly code driven).



### Settings > Debug
* **Debug_shooting_rays:** Will show debug traces on the editor (Used for tweaking Range, Spread and falloff).



### Settings > Underwater
* **ShootUnderWater:** Can this weapon shoot underwater.



### Settings > Skin
* **Allow_skins:** Does this weapon allow the player to load skins on it .
* **CasingsUseSkins:** Do the casings for this weapon use skins?.



### Settings > Gameplay > Auto Reload
* **AutoReload?:** Will this weapon auto reload if posible (Player has the setting enabled) (This is disabled for tools but normal weapons should have it enabled).