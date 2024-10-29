FROM ubuntu:20.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y \
    g++ \
    gfortran \
    make \
    cmake \
    autoconf \
    automake \
    m4 \
    bison \
    flex \
    git \
    freeglut3-dev \
    liblapack-dev \
    libhdf5-dev \
    libgsl-dev \
    wget \
    unzip \
    patch \
    libmpich-dev \
    python3 \
    gdb \
    libboost-all-dev \
    libfftw3-dev \
    libpetsc-dev \
    libslepc-dev \
    libmumps-dev \
    coinor-libipopt-dev \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# FreeFEM++ 설치
RUN wget https://github.com/FreeFem/FreeFem-sources/archive/v4.9.tar.gz \
    && tar -xzf v4.9.tar.gz \
    && cd FreeFem-sources-4.9 \
    && autoreconf -i \
    && ./configure \
    && make \
    && make install \
    && cd .. \
    && rm -rf FreeFem-sources-4.9 v4.9.tar.gz

WORKDIR /freefem
