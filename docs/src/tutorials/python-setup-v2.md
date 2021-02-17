---
layout: post
title:  Snakes and Ladders II - Snakes Reloaded
date:   2019-05-07 20:16:00 -0400
categories:
  - python/tutorial
tags:
  - hello world
  - python
---

### Topics covered
0. [TL;WR](#tl-wdr)
1. [Python installation](#python)
2. [Virtual environments](#venv)
3. [Installing libraries with pip](#pip)
4. [Project Structure](#project-structure)


---

# Python setup tutorial

## Python Version management

### pyenv: THE python version manager

Do not install python on your own. Instead, use a version manager, like [pyenv](https://github.com/pyenv/pyenv):

```bash
curl https://pyenv.run | bash
```

### Build python prerequisites:

Before bein able to build python using pyenv, you'll probably need a bunch of tools
([See here for a reference and instructions for other OS](https://github.com/pyenv/pyenv/wiki/Common-build-problems)):

=== "Ubuntu/Debian"

    ```shell
    sudo apt-get install -y \
        build-essential \
        libssl-dev \
        zlib1g-dev \
        libbz2-dev \
        libreadline-dev \
        libsqlite3-dev \
        wget \
        curl \
        llvm \
        libncurses5-dev \
        libncursesw5-dev \
        xz-utils \
        tk-dev \
        libffi-dev \
        liblzma-dev \
        python-openssl \
        git
    ```

=== "Alpine"

    ```shell
    apk add --no-cache \
        bzip2-dev \
        coreutils \
        dpkg-dev \
        dpkg \
        expat-dev \
        findutils \
        gcc \
        gdbm-dev \
        libc-dev \
        libffi-dev \
        libnsl-dev \
        libtirpc-dev \
        linux-headers \
        make \
        ncurses-dev \
        openssl-dev \
        pax-utils \
        readline-dev \
        sqlite-dev \
        tcl-dev \
        tk \
        tk-dev \
        util-linux-dev \
        xz-dev \
        zlib-dev

    # And to use pyenv-installer
    apk add \
        git \
        curl \
        bash
    ```

=== "Arch"

    ```shell
    pacman -S --needed \
        base-devel \
        openssl \
        zlib \
        bzip2 \
        readline \
        sqlite \
        curl \
        llvm \
        ncurses \
        xz \
        tk \
        libffi \
        python-pyopenssl \
        git

    # And for ncurses5
    yay -S ncurses5-compat-libs
    ```

### Installing python versions

Use `pyenv` to install python versions. `pyenv isntall --list` will show available
versions: dev and stable, old and new. Even those outside the default implementation,
like pypy, jython, micropython, etc.

So, you know... a lot of versions

Pick one  and install:

```console
pyenv install 3.9.0
```

### Setting a custom interpreter

To set a custom python as THE python interprerer:

```console
pyenv local 3.9.0
```

This creates a `.python-version` file which tells the pyenv prompt command to ensure
that specific python is the first one found in $PATH.


## Managing Virtual Environments
