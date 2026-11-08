# 3D Web Experience Skill

A practical skill for planning and building interactive 3D experiences for the web. It focuses on choosing an appropriate rendering stack, preparing 3D assets, implementing scene interactions, and balancing visual impact with loading performance and usability.

## Capabilities

- Three.js and WebGL scene implementation.
- React Three Fiber scene composition.
- Spline-based 3D integration.
- GLB/GLTF model loading and optimization.
- Product configurators and interactive 3D previews.
- Scroll-driven camera and model interactions.
- Loading, fallback, and mobile usability considerations.

## When to Use

Use this skill when a website needs a meaningful 3D feature such as a product viewer, configurator, portfolio scene, or immersive story. Avoid adding 3D only for decoration.

## Installation

~~~bash
git clone https://github.com/Brajesh31/claude-3d-web-experience-skill.git ~/.claude/skills/3d-web-experience
~~~

## Invocation

~~~text
/3d-web-experience
~~~

Provide the target framework, scene goal, model assets, expected interactions, target devices, and performance constraints.

## Workflow

1. Define the user task that 3D improves.
2. Choose the lightest suitable 3D stack.
3. Set up the camera, lighting, and scene.
4. Prepare and optimize models and textures.
5. Implement the key interactions.
6. Add loading and runtime failure handling.
7. Test performance on representative mobile and desktop devices.
8. Provide a static alternative when 3D is unavailable or unsuitable.

## Performance and Usability Review

- Models and textures are appropriately sized.
- Draw calls and expensive materials are reviewed.
- Loading progress is communicated.
- The page remains usable while 3D assets load.
- Touch, keyboard, and reduced-motion behavior are considered.
- Essential product information remains available outside the canvas.
- A fallback is available when WebGL cannot initialize.

## Included Companion Resources

- [Implementation checklist](resources/implementation-checklist.md)
- [Troubleshooting guide](resources/troubleshooting.md)

## Repository Structure

~~~text
claude-3d-web-experience-skill/
├── SKILL.md
├── README.md
├── LICENSE
└── resources/
    ├── implementation-checklist.md
    └── troubleshooting.md
~~~

## License

Released under the MIT License. Copyright (c) 2026 Brajesh Kumar. See the root `LICENSE` file for the complete terms.
