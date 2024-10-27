# opengl-starter

This repository can be used as a starter template for [learnopengl.com](https://learnopengl.com/).

## Requirements
- [GLFW dependencies](https://www.glfw.org/docs/3.3/compile.html#compile_deps)
- [CMake](https://cmake.org/) (preferably latest version)
- [clangd](https://clangd.llvm.org/insAtallation#editor-plugins) editor plugin (optional)
- [clang](https://clang.llvm.org/) or [gcc](https://gcc.gnu.org/)

## How to build

1. Initialize cmake.

```bash
$ cmake -S . -B build
```

2. Build target, for example `hellowindow`.

```bash
$ cmake --build build --target hello_window
```

## License

[MIT](LICENSE)
