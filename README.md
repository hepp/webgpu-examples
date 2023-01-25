Visit the live demo at: [https://wgsl.xyz/demo](https://wgsl.xyz/demo)


The purpose of this project is to provide clear and consistent examples that:

- Are actively maintained and updated alongside the ongoing WebGPU changes.
- Are composed of a single file, with all the needed JS and shader code included inline.
- Are consident and clearly written without the need for excessive comments. 
- Run directly in HTML without referencing Typescript or other framework code.
- Do not rely on external dependencies (glMatrix is the one exception).


## Using WebGPU

WebGPU with Chrome: [Enabling via about://flags](https://developer.chrome.com/en/docs/web-platform/webgpu/#enabling-via-aboutflags) using the   `#enable-unsafe-webgpu`  at  `about://flags`.

Use [Chrome Canary](https://www.google.com/chrome/canary/) for the most recent WebGPU changes.

More up to date details for [additional browser support](%28https://caniuse.com/webgpu%29).

Tips on how to [run and view files locally](https://threejs.org/docs/#manual/en/introduction/How-to-run-things-locally).


## Sources

The WebGPU examples were derived from the following sources:

- https://github.com/austinEng/webgpu-samples/
- https://gpuweb.github.io/gpuweb/explainer/
- https://web.dev/gpu-compute/

[glMatrix](https://github.com/toji/gl-matrix) is the single dependency, it's included to reduce redundant matrix-math code required for rendering 3D examples. 