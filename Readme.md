## <span class="logo"><a href="../">!=</a></span> ar simulation
> Build AR apps with confidence.  
Iterate fast, right in Editor.  
Non-invasive, drop-in solution.  

### What is this?
ARSimulation is a custom XR backend built on top of the [XR plugin architecture](https://blogs.unity3d.com/2020/01/24/unity-xr-platform-updates/).  

It basically allows you to fly around in the Editor and test out your AR app, without having to change any code or structure. Import the package and go.

[![Zero Setup](wiki/images/simple-explanation.gif)](https://youtu.be/3b0rXkKGPF8)
*This scene only uses ARFoundation features.*

Because it's just another XR Plugin, it works with your existing app, ARFoundation, XR Interaction Toolkit, and even MARS. Zero code changes or setup needed!

### Quick Start
- Add the ARSimulation package to your project
- Open any scene that is set up for ARFoundation, or set up a new one with 
- Press Play
- Press RMB <span class="inline-image">![Right Mouse Button](wiki/images/right-click.svg)</span> + Use WASD to move around,  
LMB <span class="inline-image">![Left Mouse Button](wiki/images/left-click.svg)</span> to click/touch/interact with your app
- Done.

#### Need more tracked planes?
- drop SimulatedPlane prefab into the scene in Edit or Play Mode
- move and adjust as necessary  

[Video: Custom Planes](https://youtu.be/I5LUYohV8oI)  
[Video: Runtime Adjustments](https://youtu.be/eS9v0dSpYQk)

The same works for Point Clouds.  
(Tracked 3D Objects Coming Soon™)

#### Working with Image Tracking?
- just press play, if your scene uses image tracking a Simulated Tracked Image is generated for you.
- if you're using more than one tracked image, generate them with Empty GameObject + SimulatedARTrackedImage of your choice
  (needs to be in a ReferenceImageLibrary of course)


#### Want to test against a more complicated scenery?
- add your geometry, ideally as Prefab
- add a SimulatedReality component to it
- press Play
- done.
- (background camera image injection is experimental, but regular geometry "just works")

[Video: Complex Environment Simulation](https://youtu.be/nPvPdRppIpY)

Import the Sample " for a nicely dressed apartement as starting point.

#### URP example
[![URP Sample scene as Environment](wiki/images/urp-yt-preview.jpg)](https://youtu.be/RLLoR3mZ_fg)

#### Works great with
- Device Simulator (but works without)
- Input System: both (but works with old/new/both)

In fact, we tested a lot of configurations:

| Unity Version | Input System |      |     | ARFoundation |             | Interaction Mode |                  |
|---------------|--------------|------|-----|--------------|-------------|------------------|------------------|
|               | Old          | Both | New | 3.1          | 4.0          | Game View        | Device Simulator<sup><a href="#table-sup-1">1</a></sup> |
| 2019.3        | ✔️           | ✔️   | ✔️  | ✔️           | ✔️          | ✔️               | ✔️               |
| 2020.1b       | ✔️           | ✔️   | ✔️  | ✔️           | ✔️          | ✔️               | ✔️               |
| 2020.2a       | ✔️           | ✔️   | ✔️  | ✔️           | ✔️          | ✔️               | ✔️               |

| Unity Version | Render Pipeline |           |                 | Platform |                   |               |
|---------------|-----------------|-----------|-----------------|----------|-------------------|---------------|
|               | Built-in        | URP       | HDRP<sup><a href="#table-sup-2">2</a></sup> | Editor   | iOS/Android Build<sup><a href="#table-sup-3">3</a></sup> | Desktop Build<sup><a href="#table-sup-4">4</a></sup>                |
| 2019.3        | ✔️              | ✔️        | not tested      | ✔️      |  ✔️                                         | not tested / future work     |
| 2020.1b       | ✔️              | ✔️        | not tested      | ✔️      |  ✔️                                         | not tested / future work     |
| 2020.2a       | ✔️              | ✔️        | not tested      | ✔️      |  ✔️                                         | not tested / future work     |

<sup id="table-sup-1">1</sup> Recommended. Feels very nice to use, and gives correct sizes for UI etc.  
<sup id="table-sup-2">2</sup> HDRP is not supported by Unity on iOS/Android currently.  
<sup id="table-sup-3">3</sup> "Support" here means: ARSimulation does not affect your builds, it is purely for Editor simulation.  
<sup id="table-sup-4">4</sup> We haven't done as extensive testing as with the others yet. This is very useful for multiplayer scenarios.

#### Technical Stuff

ARSimulation is a XR Plugin that works with Unity's XR SDK infrastructure and thus plugs right into ARFoundation and other systems in the VR/AR realm inside Unity. 

![XR Architecture - ARSimulation](wiki/images/XRArchitecture-ARSimulation.png)
*Currently supported features are marked orange.*

This architecture has some advantages:
- ARSimulation will not clutter your project
- it does not show up at all in your compiled app (otherwise it's a bug)
- easier to maintain with future ARFoundation changes
- requires zero changes 🤞 for working with other plugins that use ARFoundation

### Known Issues
- camera background is supported (with custom 3D scenes), but no occlusion support right now
- environment cubemap support is platform-specific  
  (Unity bug, [Issue Tracker Link](https://issuetracker.unity3d.com/product/unity/issues/guid/1215635))
- no support for simulating faces, people, or collaboration right now  
  (let us know if you feel this is important to you!)
- partial support for meshing simulation  
  (some support, but not identical to specific devices)
- touch input is single-touch for now, waiting for Unity to support it better  
  (Device Simulator only supports single touch, since Input.SimulateTouch only supports one)
- if your scene feels to dark / does not use environment lighting, make sure "Auto Generate" is on in Lighting Window or bake light data.  
  (spherical harmonics simulation will only work if the shaders are aware that they should use it)
- ARFoundation 4 logs warnings in Editor:  
  "No active UnityEngine.XR.XRInputSubsystem is available. Please ensure that a valid loader configuration exists in the XR project settings."
  We have no idea what that means, [Link to Forum Thread](https://forum.unity.com/threads/warnings-in-editor-when-using-custom-xrsystem.908852/)

### But there is also MARS now!

**Long story short:**
- If you are starting a new project, are new to AR dev, are building a very complex AR app with multiple planes and dynamic content distribution, then MARS might be a good fit.  
- If you have an existing project, are fine with ARFoundation`s feature set, are using other extensions on top of ARFoundation, are building a relatively simple AR app, don't want to shell out 600$/year/seat, ARSimulation might be helpful.

> MARS: A Framework for Simplified, Flexible AR Authoring  

Unity describes MARS (Mixed and Augmented Reality Studio) as "a framework for simplified, flexible AR authoring". We were active alpha testers, trying to use it for our own AR applications, and started developing our own solution in parallel. After a while, we stopped using MARS (besides of course testing and giving feedback to new releases).  

MARS is very ambitious and future-facing. It tries to anticipate many new types of devices and sensors, and to do that, reinvents the wheel (namely: ARFoundation) in many places.  
It wraps _around_ ARFoundation instead of extending it, which is great for some usecases but makes it very heavy for others.  
A core concept of MARS is _Functionality Injection_, which at its base feels pretty similar to what the XR SDK system is trying to achieve (note: FI might allow for more complex scenarious, but solves a similar problem of device-specific implementations.)

![XR Architecture - MARS](wiki/images/XRArchitecture-Mars.png)

> ARSimulation: A non-invasive Editor Simulation Backend

Our goal are fast iteration times in the Editor for a range of AR applications we and partner companies build. These usually consist of placing and interacting with objects from different angles. We just needed a way to "simulate" an AR device in the Editor, not a full-blown additional framework!  

Fortunately, Unity provides the ability to build exactly that using the [XR plugin architecture]()(https://blogs.unity3d.com/2020/01/24/unity-xr-platform-updates/): a custom XR provider that works in the Editor and Desktop builds.

#### Cons of MARS
- adds 6 packages to your project
- contains everything: custom tooling, custom handles, massive settings constructs, code generators, file system watchers, a completely custom provider backend, ...
- initial setup: just adding MARS packages creates >50 new files in your project (+50 more for .meta files)
    - 5 new top-level folders in your project
    - 27 different ScriptableObjects with settings
    - 18 code-generated scripts with defines etc.
    - new tags
    - some asmdefs
    - etc.
- once you start using MARS, there isn't really a way back
- MARS wraps around ARFoundation instead of extending it. This means it's not really feasible to use it for existing projects, unless you plan on converting a bunch of things to new components and 

### Open Issues on Unity's end
Unfortunately it seems nobody at Unity anticipated someone building custom XR providers in C# that are actually supposed to work in the Editor. It's advertised as a "way to build custom C++ plugins" only.  

This has lead to funny situations where we reporting bugs around usage in Editor (e.g. of the ARFoundation Samples, XR Interaction Toolkit, and others), and Unity telling us that these "don't matter since you can't use them in Editor anyways". Well guys, we hope now you see why we were asking.  
  
- Device Simulator has no way to do multitouch simulation (usually a must for any touch simulator). This means that rotating in ARFoundation isn't working out of the box in Editor right now. We are currently using LeanTouch as a workaround, as that gives proper multitouch simulation support in both Game View and Device Simulator.
- There's a number of warnings around subsystem usage in Editor. They seem to not matter much but are annoying (and incorrect).
- There's an open issue with Cubemap creation in Editor (necessary for Environment Probe simulation). [Issue Tracker](https://issuetracker.unity3d.com/product/unity/issues/guid/1215635)
- Device Simulator disables Mouse input completely - we're working around that here but be aware when you try to create Android / iOS apps that also support mouse. [Forum Thread](https://forum.unity.com/threads/new-device-simulator-preview.751067/page-4#post-5952482)
- in 2020.1 and 2020.2, even when you enable "New Input System", the Input System package is not installed in package manager. You have to install it manually. [Forum Thread](https://forum.unity.com/threads/new-input-system-not-installed-in-2020-1-after-enabling-it.908027/)
- switching from a scene with Object Tracking to a scene with Image Tracking on device crashes Android apps (we'll report a bug soon)

### Contact

[Forum Thread — ARSimulation]()

<b>[needle — tools for unity](https://needle.tools)</b>
[@NeedleTools](https://twitter.com/NeedleTools)
[@marcel_wiessler](https://twitter.com/marcel_wiessler)
[@hybridherbst](https://twitter.com/hybdridherbst)