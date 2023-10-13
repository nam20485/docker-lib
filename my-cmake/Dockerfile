FROM debian:bookworm-20230522-slim AS build

# install dependencies
RUN DEBIAN_FRONTEND=noninteractive apt-get update && \
    apt-get install -y --no-install-recommends \
        gpg \
        curl \
        apt-transport-https \
        build-essential \
        ca-certificates \
        cmake \            
        g++ \
        ninja-build \
        python3-dev \     
        mingw-w64 \        
        swig \
        build-essential \
        git \
        cmake \
        zip \
        unzip \
        tar  \
        pkg-config && \
    rm -rf /var/lib/apt/lists/* 

# install vcpkg
WORKDIR /root/src/github/microsoft
RUN git clone https://github.com/Microsoft/vcpkg.git
WORKDIR /root/src/github/microsoft/vcpkg
RUN ./bootstrap-vcpkg.sh

# set VCPKG_ROOT
ENV VCPKG_ROOT=/root/src/github/microsoft/vcpkg