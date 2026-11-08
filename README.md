# 3D Web Experience Skill

A practical skill for planning, building, and improving interactive 3D experiences on the web. It focuses on choosing an appropriate 3D stack, preparing web-ready assets, implementing scenes, creating scroll-linked interactions, and protecting performance and usability.

## What This Skill Covers

- **Three.js:** Browser-based 3D rendering and scene implementation.
- **React Three Fiber:** React-based scene composition and interaction.
- **Spline:** Design-led 3D scenes and embedded experiences.
- **WebGL:** Rendering considerations and performance-aware implementation.
- **3D assets:** GLB/GLTF, FBX, OBJ, and USDZ workflows.
- **Product experiences:** Configurators, model previews, and interactive product presentation.
- **Motion:** Scroll-driven camera, model, and material changes.
- **Experience quality:** Loading feedback, mobile support, and avoiding unnecessary 3D.

## When to Use This Skill

Use it when a task involves:

1. Adding an interactive 3D scene to a website.
2. Building a 3D product configurator or model viewer.
3. Creating a 3D portfolio or immersive landing page.
4. Selecting between Spline, Three.js, and React Three Fiber.
5. Preparing, compressing, or loading 3D assets.
6. Connecting scroll interactions to a 3D scene.
7. Improving the usability or performance of an existing WebGL experience.

Do not use it for ordinary page layout work when 3D does not materially improve the result.

## Installation

Clone the repository into the skills directory used by your agent:

```bash
git clone https://github.com/Brajesh31/claude-3d-web-experience-skill.git ~/.claude/skills/3d-web-experience
```

The skill instructions are in `SKILL.md`.

## Invoking the Skill

In a compatible Claude Code environment, invoke:

```text
/3d-web-experience
```

Describe the goal, framework, available assets, desired interaction, target devices, and performance constraints. The more specific the constraints, the more useful the implementation guidance will be.

## Recommended Project Workflow

### 1. Decide Whether 3D Is Necessary

Start with the user task, not the visual effect. Decide whether a model, spatial interaction, or animation provides information or functionality that a conventional image or interface cannot provide as effectively.

### 2. Select the Stack

| Situation | Suitable starting point |
|---|---|
| Designer-led scene and fast prototyping | Spline |
| Existing React application | React Three Fiber |
| Framework-independent custom scene | Three.js |
| Game-like 3D requirements | Evaluate Babylon.js alongside Three.js |

Treat this as a starting guide, not a universal ranking. Confirm the project's deployment environment, interaction complexity, asset pipeline, and team skills.

### 3. Prepare Assets

Prefer web-appropriate formats such as GLB/GLTF where suitable. Inspect geometry, materials, textures, animation, licensing, and file size before integration. Reduce asset complexity only after checking visual quality.

### 4. Implement the Scene

Build the scene in small steps: camera, lighting, geometry or model loading, controls, and then interaction. Keep essential page content and actions in regular accessible HTML rather than hiding everything inside the canvas.

### 5. Add Loading and Failure States

Show meaningful loading feedback for large assets. Handle asset failures and WebGL initialization failures separately. A loading fallback alone does not handle runtime errors.

### 6. Optimize Against Real Devices

Measure loading time, frame time, memory, draw calls, and responsiveness on representative desktop and mobile devices. Do not treat a generic triangle count or FPS target as a guarantee.

### 7. Provide an Alternative

Provide a useful static or simplified experience when 3D is unavailable, too slow, or disabled. Respect reduced-motion preferences and keep controls usable by keyboard and touch where applicable.

## Performance Review Checklist

- [ ] 3D serves a clear user purpose.
- [ ] Models and textures are appropriately sized.
- [ ] Compression is tested for visual quality and decoder compatibility.
- [ ] Draw calls, material count, and rendering work are reviewed.
- [ ] Loading progress is visible for substantial assets.
- [ ] Failed asset loads have a recovery or fallback state.
- [ ] WebGL initialization failure is handled.
- [ ] Device pixel ratio is measured and constrained where needed.
- [ ] Mobile performance is tested on real devices.
- [ ] Reduced-motion preferences are respected.
- [ ] Rendering pauses or becomes lighter when practical and idle.
- [ ] Essential content remains available outside the canvas.

## Usability Review Checklist

- [ ] The purpose of the scene is clear.
- [ ] Camera and object controls are discoverable.
- [ ] Controls behave sensibly on touch screens.
- [ ] Keyboard access is considered.
- [ ] The scene does not trap ordinary page scrolling unexpectedly.
- [ ] Loading, error, and fallback states are understandable.
- [ ] Essential product information and actions remain accessible without 3D.

## Repository Structure

```text
claude-3d-web-experience-skill/
├── SKILL.md
├── README.md
├── LICENSE
└── resources/
    ├── implementation-checklist.md
    └── troubleshooting.md
```

The two files under `resources/` are supplemental practical guides included with this repository. They are not additional source files exposed by the AITMPL skill page.

## Included Resources

### Implementation Checklist

See [resources/implementation-checklist.md](resources/implementation-checklist.md) for a step-by-step review covering scene planning, asset preparation, React Three Fiber setup, interaction, performance, accessibility, and release checks.

### Troubleshooting Guide

See [resources/troubleshooting.md](resources/troubleshooting.md) for practical diagnosis of blank canvases, model loading failures, poor frame rates, scroll conflicts, and mobile rendering issues.

## Example Use Prompts

**Choose a stack**

```text
I am building a product page in React. Compare Spline and React Three Fiber for an interactive product viewer. Recommend one based on maintainability, loading performance, mobile support, and required controls.
```

**Review a 3D scene**

```text
Review this Three.js scene for loading performance, draw calls, memory use, accessibility, mobile behavior, and failure handling. Separate confirmed problems from assumptions and propose prioritized fixes.
```

**Plan an immersive portfolio**

```text
Plan a scroll-driven 3D portfolio experience. Keep project details readable in HTML, respect reduced motion, support mobile devices, and define a static fallback.
```

## Important Notes

- Code snippets in the skill are illustrative patterns. Adapt imports, component boundaries, and asset paths to the installed project versions.
- The placeholder Spline URL and model paths must be replaced with actual authorized assets.
- Performance budgets must be measured on the target hardware. A single polygon or FPS threshold is not universally reliable.
- Review the licenses and usage terms of 3D models, textures, fonts, and other assets before shipping them.
- The skill does not ship application code, 3D models, or runtime dependencies.

## License

The repository includes an MIT license. Review the license file and ensure that the repository's contents are eligible for distribution under it.
