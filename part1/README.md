# Part 1: Getting Started: Parts of the code and Builing

## Introduction

This part of the workshop will cover the different parts of the code and how to build the project. 
The goal is to provide a good overview of the different parts of the OBS Plugin Template and how to use them.
It will also cover the different parts of the OBS plugin API and how to use them.
Specifically, it will cover registring a plugin with OBS, adding properties to the plugin, and accessing those properties in code.
This information will be used in later parts of the workshop.

## Types of OBS Plugins
- Source (includes filters)
- Output
- Encoder
- Service

## Parts of a plugin
- Common Directory Structure
- Key descriptive plugin information in `CMakeLists.txt` and `buildspec.json`
- `CMakelists.txt` - what to edit and what not to edit
- Where custom source code goes (`src`)
- Where to put resources (e.g. data files) and finding them in code (`obs_find_module_file`)
- Where to put translation .ini files and accessing them in code (`obs_module_text`)

## Mechanics of a plugin
- Module registration (`obs_register_module`)
- Plugin registration (e.g. `obs_source_info`)
- Initialization (`obs_module_load` and `obs_source_info.create`)
- Shutdown (`obs_module_unload` and `obs_source_info.destroy`)
- Suspension (`obs_source_info.activate` and `obs_source_info.deactivate`)
- Logging (using `blog`)

## Settings and Properties
- Properties (`obs_source_info.get_properties`, `obs_source_info.get_defaults`, `obs_source_info.update`)
- Properties in the UI and access in code (`obs_properties_add_X`, `obs_data_get/set_X`)
- Settings - used to persist data to disk (`obs_data_t`, `obs_data_create`, `obs_data_get/set_X`)

## Building the plugin
- CMake
- GitHub actions and workflows (`.github/workflows` and `./github/actions`)
- Build scripts (`.github/scripts/build-<OS>.sh`)
- Pre-built dependencies (`buildspec.json`)
- Packaging (`.github/scripts/package-<OS>.sh` files)
- Signing the plugin
