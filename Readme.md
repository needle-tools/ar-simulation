# AR Simulation
> Build AR apps with confidence.  
Iterate fast, right in Editor.  
Non-invasive, drop-in solution.  
Fair pricing.  

<a href="#quick-start-">Quick&nbsp;Start</a>&nbsp;⚡ • 
<a href="#license--pricing-">License&nbsp;&&nbsp;Pricing</a>&nbsp;💸 • 
<a href="#documentation-">Documentation</a>&nbsp;📜
  
<a href="#technical-details-">Technical&nbsp;Details</a>&nbsp;🔎 • 
<a href="#but-there-is-also-mars-now-">Comparison&nbsp;to&nbsp;MARS</a>&nbsp;🚀 • 
<a href="#related-solutions-">Related&nbsp;Solutions</a>&nbsp;👪 • 
<a href="#contact-%EF%B8%8F">Say&nbsp;hi</a>&nbsp;✍️

## What is this?
  
This package allows you to fly around in the Editor and test your AR app, without having to change any code or structure. Iterate faster, test out more ideas, build better apps.  
ARSimulation is a custom XR backend, built on top of the [XR plugin architecture](https://blogs.unity3d.com/2020/01/24/unity-xr-platform-updates/).

[![Zero Setup](../../wiki/images/simple-explanation.gif)](https://youtu.be/3b0rXkKGPF8)  
*This scene only uses ARFoundation features.*

Because it's just another XR Plugin and we took great care to simulate important features, it works with your existing app, ARFoundation, XR Interaction Toolkit — zero changes to your code or setup needed! ✨  
And if you need more control, there's a lot of knobs to turn. 

## Quick Start ⚡
- Install ARSimulation by dropping this package into Unity 2019.3+:  
  [📦 ARSimulation Installer](https://github.com/needle-tools/ar-simulation/releases/download/release%2F1.0.0-preview.5/ARSimulationInstaller.unitypackage)
- Open any scene that is set up for ARFoundation or click ``Tools/AR Simulation/Convert to AR Scene``
- Press Play
- Press `RMB (Right Mouse Button)` + Use `WASD` to move around,  
`LMB (Left Mouse Button)` to click • touch • interact with your app
- Done.  

## License & Pricing 💸  
Using ARSimulation **requires you to buy a per-seat license** —  
please buy seats for your team through Unity AssetStore (link coming soon).  
This is a single $60 payment, not a monthly subscription.  

You can use it for 7 days **for evaluation purposes only**,  
without buying a license. We trust you. 🧐  

## Documentation 📜

We are working on improving the docs right now and making some nice "Getting Started" videos. Stay tuned — until then, here's some things you might need:

### Found a bug? 😅 Missing a feature?  
Please [open an issue](https://github.com/needle-tools/ar-simulation/issues/new/choose) and tell us about it! We want this to be as useful as possible to speed up your workflow.

### Need more tracked planes? ✈
- Drop the `SimulatedPlane` Prefab into the scene in Edit or Play Mode (or just add another ``SimulatedARPlane`` component)
- Move and adjust as necessary  

[Video: Custom Planes](https://youtu.be/I5LUYohV8oI)  
[Video: Runtime Adjustments](https://youtu.be/eS9v0dSpYQk)

The same works for Point Clouds.  
(Tracked 3D Objects Coming Soon™)

### Working with Image Tracking? 🖼
- Just press play, if your scene uses image tracking a `Simulated Tracked Image` is generated for you.
- If you're using more than one tracked image, generate them with `Empty GameObject` + `SimulatedARTrackedImage` of your choice
  (needs to be in a `ReferenceImageLibrary` of course)


### Want to test against a more complicated scenery? 🏰
- Add your geometry, ideally as Prefab
- Add a `SimulatedReality` component to it
- Press Play
- Done.
- (Background camera image rendering 📷 is experimental right now)

[Video: Complex Environment Simulation](https://youtu.be/nPvPdRppIpY)

Here's a preview of a nicely dressed apartement sample: 🏡
![sample: Example Apartment](../../wiki/images/simulated-environment.gif)

### URP example 🔨
[![URP Sample scene as Environment](../../wiki/images/urp-yt-preview.jpg)](https://youtu.be/RLLoR3mZ_fg)  
*Click preview to watch video*

### Works great with 
📱 [Device Simulator](https://github.com/needle-mirror/com.unity.device-simulator) (but works without)  

👆 Input System: both (but works with old/[new](https://github.com/needle-mirror/com.unity.inputsystem)/both) 

#### Supported Configurations

| Unity Version | Input System |      |     | ARFoundation |             | Interaction Mode |                  |
|---------------|--------------|------|-----|--------------|-------------|------------------|------------------|
|               | Old          | Both | [New](https://github.com/needle-mirror/com.unity.inputsystem) | [3.1](https://github.com/needle-mirror/com.unity.xr.arfoundation/tree/3.1.3)          | [4.0](https://github.com/needle-mirror/com.unity.xr.arfoundation/)          | Game View        | [Device Simulator](https://github.com/needle-mirror/com.unity.device-simulator)<sup><a href="#table-sup-1">1</a></sup> |
| [![](https://img.shields.io/badge/%40-2019.3/4-green.svg)](https://unity.com/de/releases/2019-3)      | ✔️           | ✔️   | ✔️  | ✔️           | ✔️          | ✔️               | ✔️               |
| [![](https://img.shields.io/badge/%40-2020.1b-green.svg)](https://unity3d.com/de/beta/2020.1b)      | ✔️           | ✔️   | ✔️  | ✔️           | ✔️          | ✔️               | ✔️               |
| [![](https://img.shields.io/badge/%40-2020.2a-green.svg)](https://unity3d.com/de/beta/2020.2a)       | ✔️           | ✔️   | ✔️  | ✔️           | ✔️          | ✔️               | ✔️               |

| Unity Version | Render Pipeline |           |                 | Platform |                   |               |
|---------------|-----------------|-----------|-----------------|----------|-------------------|---------------|
|               | Built-in        | [URP](https://github.com/needle-mirror/com.unity.render-pipelines.universal)       | HDRP<sup><a href="#table-sup-2">2</a></sup> | Editor   | iOS/Android Build<sup><a href="#table-sup-3">3</a></sup> | Desktop Build<sup><a href="#table-sup-4">4</a></sup>                |
| [![](https://img.shields.io/badge/%40-2019.3/4-green.svg)](https://unity.com/de/releases/2019-3)        | ✔️              | ✔️        | —      | ✔️      |  ✔️                                         | untested     |
| [![](https://img.shields.io/badge/%40-2020.1b-green.svg)](https://unity3d.com/de/beta/2020.1b)       | ✔️              | ✔️        | —      | ✔️      |  ✔️                                         | untested     |
| [![](https://img.shields.io/badge/%40-2020.2a-green.svg)](https://unity3d.com/de/beta/2020.2a)       | ✔️              | ✔️        | —      | ✔️      |  ✔️                                         | untested     |

<sup id="table-sup-1">1</sup> Recommended. Feels very nice to use, and gives correct sizes for UI etc.  
<sup id="table-sup-2">2</sup> HDRP is not supported by Unity on iOS/Android currently.  
<sup id="table-sup-3">3</sup> "Support" here means: ARSimulation does not affect your builds, it is purely for Editor simulation.  
<sup id="table-sup-4">4</sup> We haven't done as extensive testing as with the others yet. Making Desktop builds with ARSimulation is very useful for testing multiplayer scenarios without the need to deploy to multiple mobile devices.

![AR Simulation running in Device Simulator](../../wiki/images/device-simulator.gif)  
*ARSimulation running in Device Simulator.*

## Technical Details 🔬

ARSimulation is a `XR Plugin` that works with Unity's XR SDK infrastructure and thus plugs right into [ARFoundation](https://github.com/needle-mirror/com.unity.xr.arfoundation) and other systems in the VR/AR realm inside Unity. 

![XR Architecture - ARSimulation](../../wiki/images/XRArchitecture-ARSimulation.png)  
*Currently supported features are marked orange.*

**This architecture has some advantages:**
- ARSimulation will not clutter your project
- Does not show up at all in your compiled app (otherwise it's a bug, please let us know)
- easier to maintain with future ARFoundation changes
- Requires Zero Changes™ for working with other plugins that use ARFoundation

## Known Issues 🚧
- Camera background is supported (with custom 3D scenes), but our default shader has no occlusion support right now (same as ARFoundation by default). You can just use your own plane shaders of course that supports occlusion (see ``AR Foundation samples/Plane Occlusion`` scene)
- Environment cubemap support is platform-specific  
  (Reason: Unity bug, [Issue Tracker Link](https://issuetracker.unity3d.com/product/unity/issues/guid/1215635))
- No support for simulating faces, people, or collaboration right now  
  (let us know if you feel this is important to you!)
- Partial support for meshing simulation  
  (some support, but not identical to specific devices)
- Touch input is single-touch for now, waiting for Unity to support it better & looking into it ourselves  
  (Reason: Device Simulator only supports single touch, since Input.SimulateTouch only supports one)
- If your scene feels to dark / does not use environment lighting, make sure `Auto Generate` is on in Lighting Window or bake light data.  
  (Reason: spherical harmonics simulation will only work if the shaders are aware that they should use it)
- ARFoundation 4 logs warnings in Editor:  
  ``No active UnityEngine.XR.XRInputSubsystem is available. Please ensure that a valid loader configuration exists in the XR project settings.``
  We have no idea what that means: [Link to Forum Thread](https://forum.unity.com/threads/warnings-in-editor-when-using-custom-xrsystem.908852/)  
- ARSimulation currently has a dependency on `XRLegacyInputHelpers` that isn't needed in call cases; we will remove that dependency in a future release.  

## But there is also MARS now! 🔭

**Long story short:**
- If you are starting a new project, are new to AR dev but have a lot of financial resources, are building a very complex AR app with multiple planes and dynamic content and constraints between objects, then MARS might be a good fit.  
- If you have an existing project, are fine with ARFoundation`s feature set, are using other extensions on top of ARFoundation, are building a relatively simple AR app, don't want to shell out 600$/year/seat, ARSimulation might be helpful.

### MARS: A Framework for Simplified, Flexible AR Authoring  

Unity describes [MARS (Mixed and Augmented Reality Studio)](https://unity.com/de/products/mars) as "a framework for simplified, flexible AR authoring". We were active alpha testers, trying to use it for our own AR applications, and started developing our own solution in parallel. After a while, we stopped using MARS (besides of course testing and giving feedback to new releases).  

MARS is very ambitious and future-facing. It tries to anticipate many new types of devices and sensors, and to do that, reinvents the wheel (namely: basic ARFoundation features) in many places.  
It wraps _around_ ARFoundation instead of extending it, which is great for some usecases but makes it very heavy for others.  
A core concept of MARS is _Functionality Injection_, which at its base feels pretty similar to what the XR SDK system is trying to achieve (note: FI might allow for more complex scenarious, but solves a similar problem of device-specific implementations.)

![XR Architecture - MARS](../../wiki/images/XRArchitecture-Mars.png)

### ARSimulation: A non-invasive Editor Simulation Backend

Our goal are fast iteration times in the Editor for a range of AR applications we and partner companies build. These usually consist of placing and interacting with objects from different angles. We just needed a way to "simulate" an AR device in the Editor, not a full-blown additional framework!  

Fortunately, Unity provides the ability to build exactly that using the [XR plugin architecture](https://blogs.unity3d.com/2020/01/24/unity-xr-platform-updates/): a custom XR provider that works in the Editor and Desktop builds.  
There were quite some challenges, especially around Input System support (we support old/both/new modes now) and touch injection (there's a private Input.SimulateTouch API that is also used by the DeviceSimulator package).  
Plus, the usual amount of Unity bugs and crashes; we are pretty confident that we worked around most of them and sent bug reports for the others.

### Comparison between MARS and ARSimulation ⚔
| ⚔ | ARSimulation | MARS |
| -- | -- | -- |
| Claim | Non-invasive editor simulation backend for ARFoundation | Framework for simplified, flexible AR Authoring |
| Functionality | XR SDK plugin for Desktop:<br>positional tracking simulation, touch input simulation, image tracking, ... | Wrapper around ARFoundation with added functionality: <br>custom simulation window, object constraints and forces, editor simulation (including most of what ARSimulation can do), file system watchers, custom Editor handles, codegen, ... |
| Complexity | <ul><li>1 package</li><li>no additional files in project,<br>only for XR SDK configuration</li><li>< 80 Types</li></ul> | <ul><li>6 packages</li><li>5 new top-level folders in your project</li><li>> 800 Types and classes</li><li>27 different ScriptableObjects with settings</li><li>18 code-generated scripts with defines etc.</li></ul> |
| Changes to project | none |  |
| Required changes | none | ARFoundation components need to be replaced with their MARS counterparts |
  
**The following table compares ARSimulation and MARS in respect to in-editor simulation for features available in ARFoundation.**  
Note that MARS has a lot of additional tools and features (functionality injection, proxies, recordings, automatic placement of objects, constraints, ...) not mentioned here that might be relevant to your usecase. See the [MARS docs](https://docs.unity3d.com/Packages/com.unity.mars@1.0/manual/MARSConcepts.html) for additional featuers.

| ⚔ | ARSimulation<br>*Simulation Features* | MARS<br>*Simulation Features* |
| -- | -- | -- |
| Plane Tracking | ✔️ | ✔️ |
| Touch Input | ✔️ | ❌<sup><a href="#comparison-table-sup-1">1</a></sup> |
| Simulated Environments | (✔️)<sup><a href="#comparison-table-sup-2">2</a></sup> | ✔️ |
| Device Simulator | ✔️ | ❌<sup><a href="#comparison-table-sup-3">3</a></sup> |
| Point Clouds | ✔️ | ✔️ |
| Image Tracking | ✔️ | ✔️ |
| Light Estimation<br>Spherical Harmonics | ✔️ | ❌ |
| Anchors | ✔️ | ❌ |
| Meshing | (✔️) | ✔️ |
| Face Tracking | ❌ | (✔️)<sup><a href="#comparison-table-sup-4">4</a></sup> |
| Object Tracking | ❌ | ❌ |
| Human Segmentation | ❌ | ❌ |


<sup id="comparison-table-sup-1">1</sup> MARS uses `Input.GetMouseButtonDown` for editor input AND on-device input. This means: no testing of XR Interaction Toolkit features, no multitouch. You can see the (somewhat embarassing) MARS input example at [this Unity Forum link](https://forum.unity.com/threads/mars-direct-placement-example.908381/). ARSimulation supports full single-touch simulation in GameView and DeviceSimulator.  
<sup id="comparison-table-sup-2">2</sup> ARSimulation's plane shader doesn't support occlusion right now, which matches what ARFoundation shaders currently do (no occlusion). You can still use your own shaders that support occlusion (see ``AR Foundation samples/PlaneOcclusion`` scene)  
<sup id="comparison-table-sup-3">3</sup> MARS uses a custom "Device View", but doesn't support the Unity-provided Device Simulator package. This means you can't test your UIs with MARS with proper DPI settings (e.g. the typical use of *Canvas: Physical Size*).  
<sup id="comparison-table-sup-4">4</sup> MARS has a concept of *Landmarks* that are created from ARKit blendshapes and ARCore raw meshes, but no direct support for either.  

## Open Issues on Unity's end 🐛
Unfortunately it seems nobody at Unity anticipated someone building custom XR providers in C# that are actually supposed to work in the Editor. It's advertised as a "way to build custom C++ plugins" only.  

This has lead to funny situations where we reporting bugs around usage in Editor (e.g. of the ARFoundation Samples, XR Interaction Toolkit, and others), and Unity telling us that these "don't matter since you can't use them in Editor anyways". Well guys, we hope now you see why we were asking.  
  
- Device Simulator has no way to do multitouch simulation (usually a must for any touch simulator). This means that rotating in ARFoundation isn't working out of the box in Editor right now. We are currently using LeanTouch as a workaround, as that gives proper multitouch simulation support in both Game View and Device Simulator.
- Device Simulator does not support tapCount (is always 1). Case 1258166
- New Input System does not support tapCount (is always 0, even on devices). Case 1258165
- Device Simulator: Simulated touches oscillate between "stationary" and "moved" in Editor (no subpixel accuracy?). Case 1258158
- There's a number of warnings around subsystem usage in Editor. They seem to not matter much but are annoying (and incorrect).
- There's an open issue with Cubemap creation in Editor (necessary for Environment Probe simulation). [Issue Tracker](https://issuetracker.unity3d.com/product/unity/issues/guid/1215635)
- Device Simulator disables Mouse input completely - we're working around that here but be aware when you try to create Android / iOS apps that also support mouse. [Forum Thread](https://forum.unity.com/threads/new-device-simulator-preview.751067/page-4#post-5952482)
- in 2020.1 and 2020.2, even when you enable "New Input System", the Input System package is not installed in package manager. You have to install it manually. [Forum Thread](https://forum.unity.com/threads/new-input-system-not-installed-in-2020-1-after-enabling-it.908027/)
- switching from a scene with Object Tracking to a scene with Image Tracking on device crashes Android apps (we'll report a bug soon)

## Related solutions 👪
Since Unity still hasn't provided a viable solution for testing AR projects without building to devices, a number of interesting projects arose to overcome that, especially for remoting.  
For our own projects, we found that device remoting is still too slow for continuous testing and experimentation, so we made ARSimulation.

[Kirill Kuzyk](https://twitter.com/kirill_kuzyk) recently released a great tool called [AR Foundation Editor Remote](https://stampedegames.wixsite.com/ar-foundation-remote) which uses a similar approach and creates a custom, editor-only XR SDK backend that injects data received from remote Android and iOS devices.  
[Here's the AR Foundation Editor Remote forum thread](https://forum.unity.com/threads/ar-foundation-editor-remote-test-and-debug-your-ar-project-in-the-editor.898433/).

[Koki Ibukuro](https://twitter.com/asus4) has also experimented with remoting data into the Unity editor for ARFoundation development. His plugin also supports background rendering.  
It's available on GitHub: [asus4/ARKitStreamer](https://github.com/asus4/ARKitStreamer).

Unity Techologies is of course also experimenting with remoting, and currently has an internal Alpha version that is undergoing user testing.  
[Here's the forum thread for the upcoming Unity AR Remoting](https://forum.unity.com/threads/ar-remoting-simulation.720575/).

And of course there's [MARS](https://unity.com/de/products/mars), the newly released, 600$/seat/year framework for simplified and flexible AR Authoring. It's probably a great solution for enterprises, and has a ton of additional tooling that goes way beyond what ARFoundation provides. We were Alpha testers of MARS and early on it became clear that it was not what many people believed it to be — a simple way to test your app without building to device. [Here's the Forum section for MARS](https://forum.unity.com/forums/unity-mars.494/).

## Contact ✍️

[Forum Thread — ARSimulation](https://forum.needle.tools/ar-simulation)

<b>[needle — tools for unity](https://needle.tools)</b> • 
[@NeedleTools](https://twitter.com/NeedleTools) • 
[@marcel_wiessler](https://twitter.com/marcel_wiessler) • 
[@hybridherbst](https://twitter.com/hybdridherbst) • 
[Say hi!](mailto:hi@needle.tools?subject=Hi!)

[![](https://img.shields.io/discord/717429793926283276?color=FF9800&label=Discord)](https://discord.gg/CFZDp4b)

