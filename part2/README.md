# Part 2: Adding a Source

## Introduction

This part of the workshop will cover adding a source to the plugin. 
The goal is to provide a good overview of the different parts of the OBS Plugin API and how to use them. 
Specifically, it will cover registering a source with OBS, the various parts of the `obs_source_info` struct, and how to use them.
Finally, we will create a simple filter source that takes a video source and renders it without any changes.

## Source plugins
- What Sources are used for (render video, audio)
- Sources can also be used for filters and transitions. 
- More information in `libobs/obs-source.h` and `obs_source_t` in `libobs/obs.h`

## Adding a source to the plugin
- `obs_source_info` struct
- `obs_register_source` function
- `obs_source_info` struct members (`.id`, `.type`, `.output_flags`, `.get_name`)
- The `.type` member (`OBS_SOURCE_TYPE_INPUT`, `OBS_SOURCE_TYPE_TRANSITION`, `OBS_SOURCE_TYPE_FILTER`)
- The `.output_flags` member (`OBS_SOURCE_VIDEO`, `OBS_SOURCE_AUDIO`, `OBS_SOURCE_ASYNC`/`OBS_SOURCE_ASYNC_VIDEO`, `OBS_SOURCE_CUSTOM_DRAW`, `OBS_SOURCE_INTERACTION`, `OBS_SOURCE_COMPOSITE`, `OBS_SOURCE_DO_NOT_DUPLICATE`)

## Source callbacks
- `obs_source_info` struct members that are functions (`.get_defaults`, `.create`, `.destroy`, `.activate`, `.deactivate`, `.video_render`, `.video_tick`, `.get_properties`, `.update`, `.get_width`, `.get_height`)
- Difference between `.video_render` (filter with graphics subsystem), `.video_tick` (called every frame with timestamp) and `.filter_video` (filter without graphics subsystem with raw pixel data)

## The "Echo" filter source
- A simple filter source that takes a video source and renders it without any changes
- `echo_source.c` and `echo_source.h`
- `echo_source_info` struct
- `.video_render` callback
- Demo of the filter source in OBS
