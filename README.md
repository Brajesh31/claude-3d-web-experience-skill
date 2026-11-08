# claude-3d-web-experience-skill

A Claude Code skill for designing and building performant, interactive 3D experiences for the web.

## Overview

This skill covers browser-based 3D experiences using Three.js, React Three Fiber, WebGL, and related workflows. It helps developers create interactive scenes, product configurators, 3D portfolios, and immersive web experiences without ignoring performance, accessibility, or usability.

3D should support the user's task. It should not be added as decoration when it makes the site slower or harder to use.

## Main Capabilities

- Build scenes with Three.js.
- Integrate React Three Fiber into React applications.
- Work with WebGL rendering.
- Load and optimize GLB and GLTF models.
- Create interactive product configurators.
- Build scroll-driven and pointer-driven interactions.
- Use Spline-based scene workflows where appropriate.
- Optimize loading, rendering, and asset size.
- Design fallbacks for unsupported or low-powered devices.

## When to Use It

Use this skill when creating:

- 3D product showcases.
- Interactive product configurators.
- 3D portfolios and landing pages.
- Immersive web experiences.
- WebGL scenes and custom interactions.
- Scroll-based 3D storytelling.

## Installation

```bash
git clone https://github.com/Brajesh31/claude-3d-web-experience-skill.git ~/.claude/skills/3d-web-experience
```

Install the 3D libraries required by the target application. Choose the lightest stack that supports the desired scene and interaction.

## Usage

Invoke the skill for web-based 3D work:

```text
/3d-web-experience
```

Provide the target framework, scene concept, model assets, interaction requirements, supported devices, and performance budget.

## Recommended Workflow

1. Define what 3D adds to the user experience.
2. Choose Three.js, React Three Fiber, or another suitable workflow.
3. Establish the scene and camera.
4. Import and optimize assets.
5. Implement the core interaction.
6. Add loading and error states.
7. Optimize geometry, textures, materials, and draw calls.
8. Test on mobile and lower-powered devices.
9. Provide a fallback where WebGL is unavailable.
10. Measure performance before release.

## Performance Checklist

- Models use appropriate geometry complexity.
- Textures are compressed and sized sensibly.
- Unnecessary draw calls are reduced.
- Rendering work is limited when the scene is idle.
- Assets load progressively.
- Animation avoids unnecessary allocations.
- Mobile performance is tested.
- Reduced-motion and fallback behavior are considered.
- The 3D experience does not block essential content.

## Usability Checklist

- Controls are discoverable.
- Camera movement is predictable.
- Loading progress is visible.
- Keyboard and touch interactions are considered.
- Essential information is available without interacting with the scene.
- The experience remains usable when 3D is unavailable.

## Repository Contents

- `SKILL.md`: Main 3D web development guidance.
- `README.md`: Stack overview, workflow, and performance checklist.

## Practical Principle

The best 3D experience is not the most complex one. It is the simplest scene that creates a meaningful improvement while remaining fast and usable.
