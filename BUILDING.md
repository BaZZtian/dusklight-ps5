# Build and developer documentation

[Back to the user guide](README.md)

## Build and validate

A Linux build host needs Python 3, Git, CMake, Ninja, Clang/LLVM, Make, Meson,
rsync, wget and unzip. Rebuilding RADV also needs the host Mesa shader-tool dependencies.

```sh
python3 ps5/tools/build.py --setup --build-radv
python3 ps5/tools/validate.py
python3 ps5/tools/package-release.py --version ps5-v0.1.0
python3 ps5/tools/package-source.py --version ps5-v0.1.0
```

A prepared Vulkan tree can be supplied with `--vulkan-dir /path/to/PS5_Vulkan`.
Dependency pins are in [ps5/dependencies.json](ps5/dependencies.json).
The full SDL3/Dawn/game build script has passed using the prepared dependencies;
a complete empty-machine RADV bootstrap has not yet been verified.

