# Readme

This repository provides automated cross-compilation of [Hamlib](https://github.com/hamlib/hamlib) for various CPU architectures(for now linux only). It checks official Hamlib releases every week and automatically builds linux binary distributions when new versions are detected.

## Usage
Pre-built Linux binaries are available in `Releases` section. Download the appropriate archive for your architecture and extract the contents to your target Linux system.

## Some details..
All binaries are built within an isolated Docker environment utilizing the Debian 9 (Stretch) base image. 

Debian 9 ships with GLIBC 2.24, ensuring compatibility with the vast majority of current Linux distributions. This version represents a conservative baseline that maximizes backward compatibility. Newer GLIBC versions maintain backward compatibility, but older versions cannot run binaries built against newer GLIBC.

Static linking(--disable-shared --enable-static) is enabled when building binaries - This produces self-contained binaries with all dependencies embedded, so it should eliminates runtime dependency conflicts on target systems.

## License
The build scripts and automation code in this repository are Unlicensed(The Unlicense). Hamlib itself is licensed under various open source licenses (GPL, LGPL). Please refer to the official Hamlib repository for details.

## Disclaimer
This repository is not affiliated with official Hamlib project. It aims to provides convenience builds for users who require pre-compiled binaries across multiple architectures.

## Misc
PRs and issues are welcomed!