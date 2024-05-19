View live demo of these examples at [https://wgsl.dev/](https://wgsl.dev/)

## Goal of The Examples

Provide clear and consistent examples that:

- Are composed of a single .html file, which includes all JS and shader code inline.
- Are able to run directly without referencing TypeScript or other framework code.
- Do not rely on external dependencies ([glMatrix](https://github.com/toji/gl-matrix) is the one exception).



# WebGPU Examples & Live Demo Editor

This project was created during my process of learning WebGPU.
As a result this project became a reconstruction and representation of the official webgpu examples from [austin-eng](https://github.com/austinEng/webgpu-samples), with a few additions and expansions added.
Also a compute example was recreated from this [web.dev article](https://web.dev/gpu-compute/), as well as a light example that was built based on the teapot setup from [webgpu-test](https://github.com/cx20/webgpu-test).

The library [glMatrix](https://github.com/toji/gl-matrix) is used as the only loaded dependency, which is included via a script tag inside each example. 

For ongoing changes the main reference is the [Official WebGPU Explainer](https://gpuweb.github.io/gpuweb/explainer/).

Open to contributions and/or suggestions for improvements.



## Using WebGPU

WebGPU with Chrome: [Enabling via about://flags](https://developer.chrome.com/en/docs/web-platform/webgpu/#enabling-via-aboutflags) using the   `#enable-unsafe-webgpu`  at  `about://flags`.

Use [Chrome Canary](https://www.google.com/chrome/canary/) for the most recent WebGPU changes.

More up to date details for [additional browser support](%28https://caniuse.com/webgpu%29).


## Viewing Examples in the Demo Editor

Live at: [https://www.wgsl.dev/editor](https://www.wgsl.dev/editor)

When viewing examples with the online editor, there are a few special considerations that are accounted for before the edited script is injected into the viewing frame.


### WGSL < script > Syntax Highlighting

Until a updated WGSL language package is widely available, the following workflow for syntax highlighting was enacted.

Each example has a including `<!-- wgsl -->` after the opening script tag.
This flags the editor to replace this line.

For example, the following: `<script id="shader-wgsl" ><!-- wgsl -->` ,
is replaced with: `<script id="shader-wgsl" type="x-shader-wgsl">` .


#### In Addition

Using `<script>` tags allow us to include the shader code inline without needing to define them as multiline strings with quotes. 

By defining the type as some form of `x-shader` - a popular naming convention is being followed.
This is simply just a way to stop the compiler from attempting to read the script content as JavaScript.


### Error Status and FPS Detection

Frames per second and error detection is displayed.
This is possible because the editor looks for and attaches extra logic to the `requestAnimationFrame` function calls.

As a result, in order for the error status and frames per second data to be correctly displayed, each example will need to contain a `requestAnimationFrame` loop. This is true even for examples that might not need to render visual changes each frame. 
