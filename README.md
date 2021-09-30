# Epitech babel docker

The images includes all you need to compile your Epitech babel project.

## Featured Tags

- ``linux``: Compile your project from a linux system. (Ubuntu)
- ``linux-arm``: Compile your project from a linux system. (Ubuntu)
- ``windows``: Compile your project from a windows system. (Windows)

## About this image

This image contains all needed packages, cmake and conan.

## How to use this image

From your computer, you can run the following command to compile your project:

- From linux
```bash
docker run -it --rm -v "$PWD:/project" epitech-babel-docker:linux /bin/bash -c "cd /project && bash"
```

- From windows
```bash
docker run -it --rm -v "$PWD:/c/project" epitech-babel-docker:windows
```

### Compile your project on windows

```
cd C:\project && mkdir build && cd build && conan install .. && C:\BuildTools\Common7\IDE\CommonExtensions\Microsoft\CMake\CMake\bin\cmake.exe .. && C:\BuildTools\Common7\IDE\CommonExtensions\Microsoft\CMake\CMake\bin\cmake.exe --build .
```

## Any issue / suggestion ?

Report it on the [issues](https://github.com/ungarscool1/Epitech-babel-docker/issues) page.
