---
sidebar_position: 1
---

# Physics-Based Magazines

:::caution
This documentation may be outdated, use with caution.
:::

The first step is to create a `Data Asset` that provides the weapon actor with necessary information about the physics-based magazine. 

Follow these steps:

1. Navigate to the appropriate folder in your Unreal Engine project.
2. Create a new `Data Asset`.
3. Select the appropriate parent class for the `Data Asset`.

Once the Data Asset is created, you can configure the following properties:

* **SM Mag:** The static mesh used for the magazine’s physics upon reload. Ensure the collision is kept simple for optimal performance.
* **Socket Location:** The weapon mesh socket where the magazine will "spawn."
* **Impact Sound:** A sound cue that defines the collision sounds for the magazine. This allows for multiple sound waves to play when the magazine collides with surfaces. (Currently not working).
* **Mag Impulse:** The physics force applied to the magazine after it spawns. (Broken as of now).
* **Physics Mass (kg):** The mass (in kilograms) assigned to the magazine upon spawning.
* **Physics Material:** This determines the magazine’s physical attributes, such as bounciness and friction. Create a new physics material to achieve different behaviors.


### Notify Driven Spawn Behavior

* **Notify Driven? (False):** The magazine will spawn once the reload animation finishes, causing a slight delay in its appearance.
* **Notify Driven? (True):** The magazine will spawn based on animation notify events, providing more precise control over the timing.

### Adding Magazine Creation Anim Notifies

1. Open the weapon animation sequence that includes a reload action.
2. Add the `Anim_ForceMag` notify to the animation timeline.
3. If the weapon reloads in third-person, check the designated box to enable this functionality. (Important!)
4. Navigate to the weapon Blueprint (BP), search for `DA_Mags`, and select the newly created Mag Data Asset.