# Installation

This guide will get you up and running with certonaut. We'll start with installing certonaut and then go over basic usage.

## Supported platforms

* Linux x86-64 (amd64)
* Linux x86-32 (i386)
* :construction: Linux aarch64 [PLANNED, IN DEVELOPMENT]
* :construction: Windows x86-64 (amd64) [PLANNED, IN DEVELOPMENT]
* :construction: Windows aarch64 (amd64) [PLANNED, IN DEVELOPMENT]

## Installing certonaut

[In the future, certonaut will offer binary downloads. These will be explained here. Right now, certonaut can only be build from source]

### Building from source

!!! note "Certonaut can be build in multiple configurations"

    Certonaut features an eBPF-based solver to automatically answer HTTP-01 challenges without webserver configuration.
    However, this solver requires several additional dependencies. You can also build a "lite" version of certonaut without these features.
    Below, you can select your intended configuration, which will show you build steps for the selected configuration.

#### Prerequisites

In order to build certonaut from source, you'll need the following tools installed on your machine:

<div class="annotate" markdown>
=== "All Features"

    * The [Rust compiler and its package manager cargo](https://www.rust-lang.org/). On most platforms, the easiest way to get them is via the official installer, [rustup](https://rustup.rs/).
    * A C/C++ compiler (1), `clang` (other compilers won't work, as eBPF requires compiler-specific features).
    * cmake, on Windows (2)
    * To build several C libraries from source (libelf, zlib, and libbpf), you also need C build tools: autoconf, autopoint, flex, bison, gawk, make and pkg-config.

=== "Lite"

    * The [Rust compiler and its package manager cargo](https://www.rust-lang.org/). On most platforms, the easiest way to get them is via the official installer, [rustup](https://rustup.rs/).
    * Any C/C++ compiler (3)
    * cmake, on Windows (4)
</div>

1. :material-hand-pointing-right: certonaut's main C/C++ dependency is aws-lc-rs. If you have trouble compiling the C libraries, you should probably review their [compilation guide](https://aws.github.io/aws-lc-rs/index.html).
2. :material-hand-pointing-right: certonaut's main C/C++ dependency is aws-lc-rs. If you have trouble compiling the C libraries, you should probably review their [compilation guide](https://aws.github.io/aws-lc-rs/index.html).
3. :material-hand-pointing-right: certonaut's main C/C++ dependency is aws-lc-rs. If you have trouble compiling the C libraries, you should probably review their [compilation guide](https://aws.github.io/aws-lc-rs/index.html).
4. :material-hand-pointing-right: certonaut's main C/C++ dependency is aws-lc-rs. If you have trouble compiling the C libraries, you should probably review their [compilation guide](https://aws.github.io/aws-lc-rs/index.html).

On Debian/Ubuntu systems, you should install Rust via [rustup](https://rustup.rs/) and obtain the C dependencies via apt-get:

=== "All Features"

    ``` sh
    sudo apt-get update
    sudo apt-get install --no-install-recommends \
        clang \
        build-essential \
        autoconf \
        autopoint \
        flex \
        bison \
        gawk \
        make \
        pkg-config
    ```

=== "Lite"

    ``` sh
    sudo apt-get update
    sudo apt-get install --no-install-recommends build-essential
    ```

#### Compiling

Ensure you have a copy of certonaut's source code on the machine you want to compile:

``` sh
git clone https://github.com/certonaut/certonaut.git
cd certonaut
```

Then use cargo to compile & install:

=== "All Features"

    ``` sh
    cargo install --all-features --path . --bin certonaut
    ```

=== "Lite"

    ``` sh
    cargo install --path . --bin certonaut
    ```

If everything is succesful, the installed `certonaut` binary should be in `~/.cargo/bin/certonaut` (which should also be in your path, if you setup Rust correctly).

## Next steps

After having installed certonaut, head over to [usage](usage.md)