<div align="center">

# Zuper Workflows<br><sub><sup><i>ComfyUI workflows for easily generating high-quality images with Z-Image Turbo.</i></sup></sub>  
<a href="https://github.com/comfy-org/comfyui" target="_blank">
  <img alt="Platform" src="https://img.shields.io/badge/platform-ComfyUI-DB2777?style=flat-square&logo=nodered&logoColor=white">
</a>
<a href="https://huggingface.co/Tongyi-MAI/Z-Image-Turbo" target="_blank">
  <img alt="Model" src="https://img.shields.io/badge/model-Z--Image%20Turbo-7C3AED?style=flat-square">
</a>
<a href="https://creativecommons.org/publicdomain/zero/1.0/" target="_blank">
  <img alt="License" src="https://img.shields.io/github/license/martin-rizzo/ZuperWorkflows?color=0077B6&style=flat-square">
</a>
<a href="https://github.com/martin-rizzo/ZuperWorkflows/commits/master/" target="_blank">
  <img alt="Last" src="https://img.shields.io/github/last-commit/martin-rizzo/ZuperWorkflows?style=flat-square">
</a>
<img src="assets/zuper-workflows-screenshot.jpg" width="90%"></img>

</div>

**Zuper Workflows** are a collection of workflows for **[ComfyUI](https://github.com/comfyanonymous/ComfyUI)**,
leveraging the power of the **[Z-Image Turbo](https://huggingface.co/Tongyi-MAI/Z-Image-Turbo)** model. They enable you
to generate spectacular images with minimal effort, offering a balance between simplicity and advanced customization.

## Table of Contents

1. [Features](#-features)
2. [Requirements](#-requirements)
3. [Workflow Parameters](#advanced-workflow-parameters)
4. [Internal Style Definitions](#%EF%B8%8F-internal-style-definitions)
5. [Project Structure](#-project-structure)
6. [License](#license)



## 💎 Features

- **Visual Styles**: 20+ preconfigured visual styles to achieve high-impact results.
- **Fast Performance**: Generates images in 10 seconds or less using popular mainstream GPUs.
- **Turbo Creativity**: Creates entirely different compositions with every seed.
- **Basic & Advanced**: BASIC workflows for quick results; ADVANCED workflows for greater control.
- **Dual Interface Modes**: Choose between spaghetti layout or the new simplified ComfyUI APP mode.
- **Modular Design**: Final workflows are built from source files for easy updates and rebuilding.


## 📦 Requirements

#### Software & Custom Nodes

* __[ComfyUI](https://github.com/Comfy-Org/ComfyUI)__ v0.27 or higher, preferably the latest available version.
* __[Z-Image Power Nodes](https://github.com/martin-rizzo/ComfyUI-ZImagePowerNodes)__ v2.1.4 or higher
* __[ComfyUI-GGUF](https://github.com/city96/ComfyUI-GGUF)__ (only if you intend to use GGUF checkpoints)

#### Checkpoints

> <sub>NOTE: Although these are the preconfigured checkpoints, any other Z-Image Turbo or Qwen3-4b  
> models should work correctly, including GGUF formats if ComfyUI-GGUF is properly installed.<sub>

* __diffusion_model:__
  * __[z_image_turbo_int8_convrot_bf16emixed.safetensors](https://huggingface.co/martin-rizzo/Z-Image-Turbo-INT8-ConvRot-ComfyUI/resolve/main/z_image_turbo_int8_convrot_bf16emixed.safetensors)__ [6.17 GB]

* __text_encoder:__
  * __[qwen3-4b_int8_convrot_fp16emixed.safetensors](https://huggingface.co/martin-rizzo/Qwen3-4B-INT8-ConvRot-ComfyUI/resolve/main/qwen3-4b_int8_convrot_fp16emixed.safetensors)__ [4.42 GB]

* __vae:__
  * __[Z-Image_half_natural_vae.safetensors](https://huggingface.co/easygoing0114/Z-Image_clear_vae/resolve/main/Z-Image_half_natural_vae.safetensors)__ [335 MB]


## Advanced Workflow Parameters

__seed__
- The initial number for random generation. Each unique seed produces a different image.
- Results in significantly more dramatic variations when __"turbo_creativity"__ is turned on.

__style__
- The visual style that defines the overall look of your final image.

__prompt__
- The text description of what you want to see, including subjects, actions, and settings.
- Avoid style keywords such as photo, comic, or blur, as the selected styles handle all visual effects automatically.

__steps__
- The number of iterations performed during the denoising process.
- The optimal setting is 8 steps. Increase this value only if you require better quality or need to fix minor hallucinations caused by __"turbo_creativity"__, keeping in mind that higher step counts result in longer render times.

__noise_shift__
- Adjusts the starting noise to generate small variations in the final image or even correct minor hallucinations.
- 0.0 is the optimal setting and is generally best left unchanged, as its effects can be unpredictable.

__turbo_creativity__
- Shakes up the generation process to produce unique and original compositions, avoiding the generic AI aesthetic.
- This option may generate hallucinations and duplicated elements, especially in high-contrast images.
- Disable it when you need highly precise and complex images.
- Enable it when exploring creative compositions that show substantial variations across different seeds.
- Using __"turbo_creativity"__ may require testing multiple seeds to find the ideal one.
- Minor defects and small hallucinations can be corrected by adjusting the __"steps"__ and __"noise_shift"__ parameters.

__brightness__
- Adjusts the overall brightness of the image.
- Positive values lighten the image, while negative values darken it.

__contrast__
- Adjusts the difference between light and dark areas in the image.
- Positive values increase contrast, making darks darker and lights lighter for a more striking appearance.
- Negative values decrease contrast, resulting in a flatter, more muted look.

__color__
- Adjusts the color saturation of the image.
- Positive values produce highly colorful images.
- If the colors appear too intense or artificial, negative values are generally recommended.

__color_warp__
- Slightly adjusts the overall color tint of the image.
- Useful for calibrating skin tones or shifting the palette toward more vibrant or extravagant hues.

__color_softness__
- Smooths color transitions across the image.
- A value of 0.0 leaves the image colors unmodified.
- Both positive and negative values soften the transitions between colors, which could give the image a more realistic appearance.

__detailed_sampling__
- Applies a different sampling method during the final steps to add finer details, although it may increase generation time.

__orientation__
- Sets the orientation of the final image, where vertical creates a portrait format and horizontal creates a landscape format.

__aspect_ratio__
- Determines the proportional relationship between the width and height of the final image.

__ck_attention__
- Enables Comfy-Kitchen attention to accelerate generation.
- Works best in newer ComfyUI versions and is recommended to stay enabled.

__zimage_turbo_file__
- The checkpoint file used for the Z-Image Turbo diffusion model.

__qwen3_4b_file__
- The checkpoint file used as the text encoder, which must be based on the Qwen3-4b model.

__vae_file__
- The checkpoint file used for the variational autoencoder.

__imprint_style_label__
- Prints the name of the selected style directly onto the image.
- Recommended to be left disabled by default.


## ⚙️ Internal Style Definitions

The `./src/*.sty.txt` files contain the style definitions. Each style is divided into 'slices', generating distinct
prompts for each diffusion stage, which enhances the originality of the final image. These files serve as the base
components from which the workflows are automatically generated using the `zmake.py` script.

There are 3 slices, delimited by the `{-----` and `-----}` tags. Each slice influences the final image differently:
 1. **CORE**: Clearly defines the overall style of the final image.
 2. **LAYOUT**: Controls composition and structure, primarily influencing color and lighting.
 3. **POLISH**: Adjusts fine pixel-level details, having a subtle overall impact.


## 📂 Project Structure

```
├── LICENSE                   # License file
├── README.md                 # This file
├── README-VSCODE.md          # VS Code specific configuration
├── ZuperAPP-advanced.json    # Final generated advanced comfyui-app
├── ZuperAPP-basic.json       # Final generated basic comfyui-app
├── ZuperWF-advanced.json     # Final generated advanced workflow
├── ZuperWF-basic.json        # Final generated basic workflow
├── ZWF-README.txt            # Plain text README included in the final .zip with the workflows
├── scripts/
│   ├── print_slice.py        # Experimental script used during development
│   ├── print_slice.sh        # Shell wrapper for print_slice.py
│   ├── zmake.py              # Core workflow generation script
│   └── zmake.sh              # Shell wrapper for zmake.py
└── src/
    ├── styles-experimental.sty.txt         # Experimental style definitions
    ├── styles-illustration.sty.txt         # Illustration style definitions
    ├── styles-miniature.sty.txt            # Miniature style definitions
    ├── styles-photo.sty.txt                # Photo style definitions
    ├── zdiscarded.sty.txt                  # Discarded style definitions
    ├── zmakefile.txt                       # Build configuration file
    ├── texts/
    │   ├── about.md                        # About section for workflow internal documentation
    │   ├── filtersettings.txt              # Filter settings for workflows
    │   ├── readme-advanced.md              # README content for ADVANCED workflows
    │   ├── readme-basic.md                 # README content for BASE workflows
    │   ├── requirements.md                 # Requirements section for workflow internal documentation
    │   └── sliceshead.txt                  # Slices header information
    └── workflows/
        ├── ZuperAPP-advanced.template.json # Template for the ADVANCED version of the comfyui-app
        ├── ZuperAPP-basic.template.json    # Template for the BASIC version of the comfyui-app
        ├── ZuperWF-advanced.template.json  # Template for the workflow ADVANCED version
        └── ZuperWF-basic.template.json     # Template for the workflow BASIC version
```


## License

This project is licensed under the Creative Commons Zero v1.0 Universal (CC0 1.0)  
See the [LICENSE](LICENSE) file for details.

---

<div align="center">
⭐ If you like what you see, give the repository a star. Your support inspires more explorations!
</div>
