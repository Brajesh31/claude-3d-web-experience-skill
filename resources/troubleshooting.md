# 3D Web Experience Troubleshooting

This guide covers common failures in browser-based 3D experiences. Check the browser console and network panel before changing multiple variables.

## Blank canvas

**Possible causes**

- WebGL context creation failed.
- The canvas has zero width or height.
- A runtime exception interrupted scene initialization.
- The camera is not pointed at the scene.
- The renderer or canvas is mounted before its container has a measurable size.

**Checks**

1. Inspect the browser console for WebGL and runtime errors.
2. Confirm that the canvas container has non-zero dimensions.
3. Render a simple mesh with a basic material.
4. Confirm the camera position, target, and clipping planes.
5. Test the browser and device with a minimal WebGL example.

**Response**

Provide a visible fallback when WebGL cannot initialize. Do not leave a blank region where the user expects useful content.

## Model does not appear

**Possible causes**

- Incorrect asset URL or deployment path.
- Unsupported or malformed model file.
- Asset request blocked by CORS or server configuration.
- Missing decoder configuration for compressed assets.
- Model is outside the camera frustum or incorrectly scaled.

**Checks**

1. Inspect the model request in the network panel.
2. Confirm the response is the actual model file, not an HTML error page.
3. Load a known-good model from the same path.
4. Check scale, position, camera, and clipping range.
5. Verify compression decoder compatibility.

## Model takes too long to load

**Possible causes**

- Large textures or geometry.
- Too many separate assets requested at once.
- Inefficient model export.
- No progressive or lazy loading strategy.

**Response**

Measure transfer size and decode time separately. Optimize textures and geometry, load only what the current view needs, and show progress for long operations. Do not assume a smaller file is automatically visually acceptable.

## Frame rate is poor

**Possible causes**

- High device pixel ratio.
- Too many draw calls or expensive materials.
- High geometry or texture complexity.
- Expensive per-frame JavaScript work.
- Too many lights or post-processing passes.
- Rendering continuously while idle.

**Checks**

1. Profile the frame and identify whether time is spent in JavaScript or GPU rendering.
2. Reduce pixel ratio and compare results.
3. Temporarily disable post-processing and complex materials.
4. Reduce visible objects and compare frame time.
5. Check for allocations, React state updates, or event handlers firing every frame.

Optimize the measured bottleneck rather than applying every optimization indiscriminately.

## Page scrolling conflicts with scene controls

**Possible causes**

- Orbit controls capture wheel or touch input.
- Canvas overlay intercepts pointer events.
- Scroll-linked animation and camera controls compete.

**Response**

Decide which interaction owns each input. Disable zoom when it is not needed, configure touch behavior deliberately, and ensure the page remains navigable. Test on actual touch devices.

## Mobile device overheats or drains battery

**Possible causes**

- High pixel ratio and resolution.
- Continuous rendering while the scene is idle.
- Heavy shaders, textures, or post-processing.
- Excessive animation and interaction work.

**Response**

Use measured adaptive quality, simplify effects, reduce render resolution, and avoid unnecessary frame updates. Offer a static fallback on devices that cannot sustain the experience.

## Scroll animation feels jittery

**Possible causes**

- Competing scroll listeners or animation systems.
- Repeated layout reads and writes.
- Expensive scene updates on every scroll event.
- Timeline lifecycle or cleanup issues.

**Response**

Use the scene framework's intended frame/update mechanism, keep scroll work small, and profile on a real device. Ensure timelines and triggers are cleaned up when components unmount.

## Loading indicator never finishes

**Possible causes**

- A model request failed.
- The loader tracks only part of the asset pipeline.
- Suspense boundaries do not cover the component that suspends.
- A decoder or dependent resource is still pending.

**Response**

Inspect network requests and loader state. Add explicit error handling. A progress indicator must have a failure state and must not spin forever after a terminal error.
