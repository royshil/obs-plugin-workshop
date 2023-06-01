# OBS Plugin Builders Workshop

## Introduction

This tutorial series is meant to help you get started with OBS plugin development. It is divided into several parts, each covering a different aspect of plugin development. The goal is to provide a good overview of the different parts of the OBS API and how to use them.

## Prerequisites
- [CMake](https://cmake.org/download/) 3.16 or later
- IDE such as VS Code or Visual Studio 2019 (Community Edition is fine)
- [obs-studio](https://obsproject.com/download) 28.0.0 or later

## Parts of the Workshop
- [Part 1: Getting Started: Parts of the code and Building](./part1/README.md) [ ] Status - In Progress
- [Part 2: Adding a Source](./part2/README.md) [ ] Status - In Progress
- [Part 3: Adding an Effect Filter](./part3/README.md) [ ] Status - In Progress
- [Part 4: Adding a Video Render Filter](./part4/README.md) [ ] Status - In Progress
- [Part 5: Adding a Video Transition](./part5/README.md) [ ] Status - In Progress
- [Part 6: Adding an Audio filter](./part6/README.md) [ ] Status - In Progress

## Building
All of the parts of this workshop are built using a single CMake project. The project is configured using a `buildspec.json` file. This file contains the name and version of the plugin as well as the version of obs-studio to use and the pre-built dependencies for Windows and macOS.

See the original [OBS Plugin Template]()'s [README](TEMPLATE_README.md) for more information on how to configure the project.

