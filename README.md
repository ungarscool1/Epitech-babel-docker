# Epitech babel docker

The images includes all you need to compile your Epitech babel project.

## Featured Tags

- ``linux``: Compile your project from a linux system. (Ubuntu)
- ``linux-arm``: Compile your project from a linux system. (Ubuntu)
- ``windows``: Compile your project from a windows system. (Windows 20H2)
- ``windows-1809``: Compile your project from a windows system. (Windows 1809)

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

- From windows 1809
```bash
docker run -it --rm -v "$PWD:/c/project" epitech-babel-docker:windows-1809
```

### Compile your project on windows

```
cd C:\project && mkdir build && cd build && conan install .. && cmake .. && cmake --build .
```

## Any issue / suggestion ?

Report it on the [issues](https://github.com/ungarscool1/Epitech-babel-docker/issues) page.
