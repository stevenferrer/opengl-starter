# opengl-starter

This repository can be used as a starter template for [learnopengl.com](https://learnopengl.com/).

## Requirements

- [CMake](https://cmake.org/) (preferably latest version)
- [clangd](https://clangd.llvm.org/installation#editor-plugins) editor plugin
- [clang](https://clang.llvm.org/) or [gcc](https://gcc.gnu.org/) (update compiler in [.clangd](.clangd))

## How to build

1. Create build directory.

```bash
$ mkdir build
```

2. Initialize cmake.

```bash
$ cmake -S . -B build
```

3. Build your target, for example `hellowindow`.

```bash
$ cmake --build build --target hellowindow
```

## License

[MIT](LICENSE)
