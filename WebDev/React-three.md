NPM Commands:

npm outdated
Check if the packages are outdated

npx gltfjsx public/models/thief.glb
Will generate an automated 3d model component for 3d usage.


-- INSTALLS --
npm install @react-three/drei
-----------------------------
A set of useful abstractions, components, and helpers for common tasks in React Three Fiber. It includes components for lights, cameras, controls, and more.
import { Clouds, Cloud, CameraControls, Sky as SkyImpl, StatsGl } from "@react-three/drei"

npm install @react-three/postprocessing
----------------------------------------
Adds post-processing effects to R3F scenes, such as bloom, depth of field, and more.
import { EffectComposer, ScanLine } from "@react-three/postprocessing";

npm install react-three-game-engine
-----------------------------------
A game engine built on top of R3F, providing a higher-level abstraction for creating games and interactive experiences.

npm install @react-three/capture
--------------------------------
A utility for capturing high-quality screenshots or rendering animations from R3F scenes.

npm install react-three-gui
---------------------------
A graphical user interface (GUI) library for React Three Fiber, allowing developers to create interactive UI elements within 3D scenes.




--- REACT FIBER ---	
```
<Mesh/>
```

you are trying to apply the OrbitControls directly to a <mesh> element. The <mesh> element is typically used for rendering a 3D object and doesn't directly handle user interactions for camera control. Therefore, you won't be able to spin the entire scene using this approach.

````
<Canvas/>
```
you have placed the <OrbitControls> component within your <Canvas>. This is the correct way to set up camera controls for your 3D scene. The OrbitControls component is responsible for allowing the user to interact with the camera, which includes panning, zooming, and rotating the view. This is why you can spin the 3D model when using the second code snippet.

```
<group/>
```
The group component is part of the Three.js library and represents a container for other objects. It doesn't have a visual representation itself but is used to group other objects together.
The scale attribute of the ``` <group> ``` scales all its children together.

```
<primitive/>
```

The primitive component is used to render 3D objects defined outside of React in JSX
The scale attribute of ``` <primitive> ``` specifically scales the 3D model.