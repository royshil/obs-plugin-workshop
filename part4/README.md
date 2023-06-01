# Part 4 - Adding a Video Render Filter

## Introduction

This part of the workshop will cover adding a video render filter to the plugin. 
The goal is to provide a good overview of the different parts of the OBS Plugin API and how to use them. 
Specifically, it will cover using the `.filter_video` callback to render async video frames without the graphics subsystem.
Finally, we will create a simple effect filter that takes a video source and uses OpenCV to render a sepia tone effect.\

## Video render filters
- The `.output_flags` member `OBS_SOURCE_VIDEO` and `OBS_SOURCE_ASYNC`/`OBS_SOURCE_ASYNC_VIDEO`
- The `.filter_video` callback
- Adding a video render filter to the plugin

## The "Sepia" OpenCV filter
- A simple filter source that takes a video source frame and renders it with a sepia tone effect
- The `obs_source_frame` struct members (`.width`, `.height`, `.format`, `.color_range`, `.color_matrix`, `.full_range`, `.data`, `.linesize`, `.timestamp`, `.audio_samples`, `.ref`, `.format`)
- Creating an OpenCV `cv::Mat` from an `obs_source_frame`
- Applying a sepia tone effect to an OpenCV `cv::Mat`
- Creating an `obs_source_frame` from an OpenCV `cv::Mat`
- Demo of the filter source in OBS

## Colorspace conversion
- The problem with colorspaces
- Using OBS's `video_scaler_x` functions to convert between the source colorspace, RGB and back
