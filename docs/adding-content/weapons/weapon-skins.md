---
sidebar_position: 1
---

# Skins

This guide assumes you are familiar with using **Substance Painter 3D**, as the provided template material is designed specifically for it.

### Template Files
You can find the template files for weapon skins at the following link:
GitHub: TA Workfiles - Skin Templates

**The folder includes:**

* A Substance Painter project file for painting.
* An FBX model for testing.
* Example textures.
* A Skin_Info.txt file containing essential details for adding the skin in-game, such as:
* Skin name.
* Skin description.
* Skin author.
* Painting time.
* Preparing for Painting

:::info
Although any painting software can be used, **Substance Painter 3D** is highly recommended, as Toaster Arena relies on merged textures for metallic and roughness values.
:::

Open the `Revolver_Template_Substance.spp` file in **Substance Painter**.
If you encounter an error stating the project is running on an older version, you can safely ignore it.
Once opened, you should see a pre-configured setup. Now you’re ready to paint!

**Painting Example**

Here’s an example combination to inspire your design. (Add visuals or examples here if applicable.)

### Exporting Your Skin

Once you’ve finished painting your skin, export it to a format compatible with Toaster Arena:

`Go to File > Export Textures in Substance Painter.`
1. Match your export settings with the recommended settings provided by Toaster Arena.
2. **Click Export** and navigate to the exported textures folder.
3. You should see files similar to this: (Insert example screenshot of exported textures)
5. Move the exported textures to your custom skin folder.

### Naming Conventions
To prevent implementation issues, you’ll need to clean up the exported texture file names to match the required naming convention:

**Format:**
`T_(Weapon Name)_(Skin Name)_(Material Type)`

### Examples:

* `T_Revolver_RedDecay_BaseColor`
* `T_Revolver_RedDecay_NormalMap`
* `T_Revolver_RedDecay_OcclusionRoughnessMetallic`
* `T_Revolver_RedDecay_Emissive`

:::caution
Rename files accordingly before proceeding!
:::

## Editing the Skin_Info.txt File
The Skin_Info.txt file contains critical details for implementing your skin in-game.

Make sure the file is named correctly and includes the following information:

Skin Name: The name of the skin.
Skin Description: A short description of how the skin looks.
Skin Author: Your username.

Once completed, your skin is ready to be implemented into the game.