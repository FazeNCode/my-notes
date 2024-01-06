<h3> What are rigs </h3>
Rigs are an array of objects, that function as bones, letting the animator animate individual
bones for character animation.

What is Gltf 
Graphics Library Transmission format (glTF) is a 3d file formant maintianed by "Khronos Group".  which has been adopted in Google for Augmented Reality(AR) useage

GLB is a binary container format of glTF. It bundles all the texture and mesh data into a single file.



--- Blender Keybinds ---

Click on the object you want to grab, and then press [g]
[g]

Highlight the object you want to move, wether the x, y, z axix. Type [r] followed by the axis
[r]  <> [x] [y] [z]

Highlight the object you want to scale, wether making it bigger or smaller type [s]
[s]


Select the vertcies with [a]
[a]


e
+
[Shift + x]
With this you can manuiplate text, making it look like 3d. 
NOTE: convert the text into mesh, in the objects drop down, before using Shift + x


f4
Opens up prefrences where then you can add adons, such as rigify

[Shift + a] 
Will open up menu to add armature rig

Highlight the 3d model and press i to change to open up Insert Keyframe Menu
[i]


To switch between Object mode and Edit mode press tab.
[tab]


-- MOVE 3D MODEL --
To give a moving effect to the 3d model. 
1. In NLA Editor, Move to the frame in the TIMELINE you want the model to move.
2. highlight the 3d model, and press [i] and insert a location
3. Move your 3d model either the y-axis or x-axis, where you want your model to move.
4. Once you moved the model, high light the model and press [i] and insert a location.
5.) Now you should have a 3d model thats moving either on the x-axis or y-axis



-- HOW TO COMBINE MUTLIPLE ANIMATIONS --



-- HOW TO LOOP ANIMATION THAT RESET --
1.) Highlight the armtature (the model)
2.) Go to graph editor (it's next to NLA editor)
3.) Go to pose mode
4.) High light all the bones
5.) Select all key frames in the graph editor
6.) Click Channel
7.) Click on [Extrapalation mode] >> [Make Cyclic]




-- FADE IN AND OUT OBJECTS --
Put a cube object and make it bigger than the 3d model you have
Click: Shading. in the top menu bar in blender
Click: Add the two [Transparent BSDF]  [Mix Shader]
Disconnect the line from [Material Output]





Material surface: Emission will make the model/scene very bright in some cases resulting in non-appliable threejs lighting effects

Meterial surface: PrincipalBSD is the correct method when it comes to applying texture to the models/scene


NLA-Editor = (Nonlinear Animation) in blender 3.6