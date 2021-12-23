FROM ubuntu:latest

RUN apt-get update &&\
    apt-get -y upgrade &&\
    ln -fs /usr/share/zoneinfo/Europe/Paris /etc/localtime && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends tzdata && \
    apt-get -y install python3-pip \
    gcc g++ make wget libgl-dev pkg-config \
    xorg-dev libx11-xcb-dev libxcb-render0-dev \
    libxcb-render-util0-dev libxcb-xkb-dev \
    libxcb-icccm4-dev libxcb-image0-dev \
    libxcb-keysyms1-dev libxcb-randr0-dev \
    libxcb-shape0-dev libxcb-sync-dev libxcb-xfixes0-dev \
    libxcb-xinerama0-dev xkb-data libxcb-dri3-dev libxcb-util-dev && \
    dpkg-reconfigure --frontend noninteractive tzdata

RUN wget https://github.com/Kitware/CMake/releases/download/v3.21.3/cmake-3.21.3-linux-x86_64.sh &&\
    chmod +x cmake-3.21.3-linux-x86_64.sh &&\
    ./cmake-3.21.3-linux-x86_64.sh --skip-license --prefix=/usr/local &&\
    rm -rf cmake-3.21.3-linux-x86_64.sh

RUN pip install conan

RUN conan profile new --detect default; \
    conan remote add bincrafters https://bincrafters.jfrog.io/artifactory/api/conan/public-conan; \
    conan config set general.revisions_enabled=1; \
    conan profile update settings.compiler.libcxx=libstdc++11 default
