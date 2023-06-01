# Part 3: Adding an Effect Filter

## Introduction

This part of the workshop will cover adding an effect filter to the plugin. 
The goal is to provide a good overview of the different parts of the OBS Plugin API and how to use them. 
Specifically, it will cover using HLSL shaders to create a filter effect and rendering the effect to the video frame.
Finally, we will create a simple effect filter that takes a video source and renders it with a sepia tone effect.

## Effect filters
- The `.video_render` and `.video_tick` callbacks

## HLSL shaders
- What HLSL shaders are used for (rendering graphics)
- Parts of an HLSL shader (vertex shader, pixel shader, input/output structs)
- HLSL shader example (sepia tone effect)
- Where to save HLSL shaders in the plugin directory (`.effect` file)
- `obs_enter_graphics` and `obs_leave_graphics` functions
- `gs_effect_t` struct
- Finding the HLSL shader and loading it in code (`obs_module_file` and `gs_effect_create_from_file`)
- Cleaning up the HLSL shader (`gs_effect_destroy`)

## Rendering the effect
- `obs_source_process_filter_begin` and `obs_source_process_filter_end` functions
- Manual rendering with `obs_source_video_render` function of the filter's "parent" (source)

## Advanced topics
- TexRender: rendering onto an offscreen texture (`gs_texrender_t` struct, `gs_texrender_create`, `gs_texrender_destroy`, `gs_texrender_reset` and `gs_texrender_begin/end` functions)
- Stage surface: getting texture pixels from GPU (VRAM) into CPU memory (RAM) (`gs_stagesurf_t` struct, `gs_stagesurface_create`, `gs_stagesurface_destroy` and `gs_stagesurface_map/unmap` functions)
- Parameters of the HLSL shader (`gs_effect_get_param_by_name`, `gs_effect_set_X`)
- Working with additional textures (`gs_texture_create`, `gs_texture_destroy`, `gs_effect_set_texture`)
