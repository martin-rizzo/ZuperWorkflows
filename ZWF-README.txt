# ZUPER Workflows!
ComfyUI workflows for easily generating high-quality images with Z-Image Turbo.


## Description

Zuper Workflows are a collection of workflows for ComfyUI, leveraging the power
of the Z-Image Turbo model. They enable you to generate spectacular images with
minimal effort, offering a balance between simplicity and advanced
customization.


## Requirements

 * Software
    - ComfyUI v0.27 or higher, preferably the latest available version.
    - Z-Image Power Nodes v2.1.4 or higher
    - ComfyUI-GGUF (only if you intend to use GGUF checkpoints)
 * Checkpoints
    - https://huggingface.co/martin-rizzo/Z-Image-Turbo-INT8-ConvRot-ComfyUI/blob/main/z_image_turbo_int8_convrot_bf16emixed.safetensors
    - https://huggingface.co/martin-rizzo/Qwen3-4B-INT8-ConvRot-ComfyUI/blob/main/qwen3-4b_int8_convrot_fp16emixed.safetensors
    - https://huggingface.co/easygoing0114/Z-Image_clear_vae/blob/main/Z-Image_half_natural_vae.safetensors


## Parameters

__seed__: The initial number for random generation. Each unique seed produces
          a different image. Results in significantly more dramatic variations
          when "turbo_creativity" is turned on.

__style__: The visual style that defines the overall look of your final image.

__prompt__: The text description of what you want to see, including subjects,
            actions, and settings. Avoid keywords such as photo, comic, or blur,
            as the selected `style` handle all visual effects automatically.

__steps__: The number of iterations performed during the denoising process.
           The optimal setting is 8 steps. Increase this value only if you
           require better quality or need to fix minor hallucinations caused
           by `turbo_creativity`, keeping in mind that higher step counts
           result in longer render times.

__noise_shift__: Adjusts the starting noise to generate small variations in the
                 final image or even correct minor hallucinations.
                 0.0 is the optimal setting and is generally best left
                 unchanged, as its effects can be unpredictable.

__turbo_creativity__: Shakes up the generation process to produce unique and
                      original compositions, avoiding the generic AI aesthetic.
                      This option may generate hallucinations and duplicated
                      elements, especially in high-contrast images.
                      Disable it when you need highly precise and complex images.
                      Enable it when exploring creative compositions that show
                      substantial variations across different seeds.
                      Using `turbo_creativity` may require testing multiple
                      seeds to find the ideal one.
                      Minor defects and small hallucinations can be corrected by
                      adjusting the `steps` and `noise_shift` parameters.

__brightness__: Adjusts the overall brightness of the image.
                Positive values lighten the image, while negative values
                darken it.

__contrast__: Adjusts the difference between light and dark areas in the image.
              Positive values increase contrast, making darks darker and lights
              lighter for a more striking appearance.
              Negative values decrease contrast, resulting in a flatter, more
              muted look.

__color__: Adjusts the color saturation of the image.
           Positive values produce highly colorful images.
           If the colors appear too intense or artificial, negative values are
           generally recommended.

__color_warp__: Slightly adjusts the overall color tint of the image.
                Useful for calibrating skin tones or shifting the palette
                toward more vibrant or extravagant hues.

__color_softness__: Smooths color transitions across the image.
                    A value of 0.0 leaves the image colors unmodified.
                    Both positive and negative values soften the transitions
                    between colors, which could give the image a more realistic
                    appearance.

__detailed_sampling__: Applies a different sampling method during the final
                       steps to add finer details, although it may increase
                       generation time.

__orientation__: Sets the orientation of the final image, where vertical creates
                 a portrait format and horizontal creates a landscape format.

__aspect_ratio__: Determines the proportional relationship between the width
                  and height of the final image.

__imprint_style_label__: Prints the name of the selected style directly onto
                         the image.

__ck_attention__: Enables Comfy-Kitchen attention to accelerate generation.
                  Works best in newer ComfyUI versions and is recommended to
                  stay enabled.

__zimage_turbo_file__: The checkpoint file used for the Z-Image Turbo diffusion
                       model.

__qwen3_4b_file__: The checkpoint file used as the text encoder, which must be
                   based on the Qwen3-4b model.

__vae_file__: The checkpoint file used for the variational autoencoder.

-----------------------------------------------------------------------
Repository: https://github.com/martin-rizzo/ZuperWorkflows  
Examples  : https://civitai.red/models/3034056/zuper-workflows  
License: Creative Commons Zero v1.0 Universal (CC0 1.0)
