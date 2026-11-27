## 🦸 Zuper Workflows [BASIC]

This workflow enhances the quality of images generated with Z-Image Turbo (ZIT). It shares the same internal functionality as the ADVANCED version but offers fewer options to avoid complex configurations. Since the workflow leverages comfy_kitchen, subgraphs, and INT8-ConvRot quantization, along with the visual features of Node 2.0, it is recommended to run the latest version of ComfyUI with all these features enabled.

## Parameters

__seed__
* The initial number for random generation. Each unique seed produces a different image.
* Results in significantly more dramatic variations when __"turbo_creativity"__ is turned on.

__style__
* The visual style that defines the overall look of your final image.

__prompt__
* The text description of what you want to see, including subjects, actions, and settings.
* Avoid style keywords such as photo, comic, or blur, as the selected styles handle all visual effects automatically.

__turbo_creativity__
* Shakes up the generation process to produce unique and original compositions, avoiding the generic AI aesthetic.
* This option may generate hallucinations and duplicated elements, especially in high-contrast images.
* Disable it when you need highly precise and complex images.
* Enable it when exploring creative compositions that show substantial variations across different seeds.
* Using __"turbo_creativity"__ may require testing multiple seeds to find the ideal one.

__brightness__
* Adjusts the overall brightness of the image.
* Positive values lighten the image, while negative values darken it.

__color__
* Adjusts the color saturation of the image.
* Positive values produce highly colorful images.
* If the colors appear too intense or artificial, negative values are generally recommended.

__orientation__
* Sets the orientation of the final image, where vertical creates a portrait format and horizontal creates a landscape format.

__zimage_turbo_file__
* The checkpoint file used for the Z-Image Turbo diffusion model.

__qwen3_4b_file__
* The checkpoint file used as the text encoder, which must be based on the Qwen3-4b model.

__vae_file__
* The checkpoint file used for the variational autoencoder.
