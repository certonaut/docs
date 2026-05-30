# Installation

This guide will get you up and running with certonaut. We'll start with installing certonaut and then go over basic usage.

## Supported platforms

* Linux x86-64 (amd64)
* Linux x86-32 (i386)
* :construction: Linux aarch64 [PLANNED, IN DEVELOPMENT]
* :construction: Windows x86-64 (amd64) [PLANNED, IN DEVELOPMENT]
* :construction: Windows aarch64 (amd64) [PLANNED, IN DEVELOPMENT]

## Installing certonaut

### Nightly / Unstable Builds

You can download unreleased, unstable versions of certonaut built from the main branch directly:

 [https://nightly.link/certonaut/certonaut/workflows/rust/main](https://nightly.link/certonaut/certonaut/workflows/rust/main).

 These binaries are ready to use single-file binaries. The binaries fully-featured builds with all functionality enabled, built on GitHub Actions for transparency. As these are unstable, they will contain more bugs and unfinished features compared to regular releases. (Note: Since certonaut is currently in alpha, no regular releases exist as of yet).

Three nightly builds exist currently:

* Linux for ARM 64-bit processors (aarch64/arm64/armv8): [https://nightly.link/certonaut/certonaut/workflows/rust/main/certonaut-linux-arm64.zip](https://nightly.link/certonaut/certonaut/workflows/rust/main/certonaut-linux-arm64.zip)
* Linux for x86-64 bit processors (Intel/AMD): [https://nightly.link/certonaut/certonaut/workflows/rust/main/certonaut-linux-x64.zip](https://nightly.link/certonaut/certonaut/workflows/rust/main/certonaut-linux-x64.zip)
* Windows for x86-64 bit processors (Intel/AMD): [https://nightly.link/certonaut/certonaut/workflows/rust/main/certonaut-windows-x64.zip
](https://nightly.link/certonaut/certonaut/workflows/rust/main/certonaut-windows-x64.zip)

To use, download the zip file for your system, unzip it, and execute the binary file (on Unix you may need to `chmod +x certonaut` the binary first). It is recommended to run certonaut as the `root` user (or with `sudo`) in order for it to be able to make changes to system files where required (e.g. for the magic solver). However, advanced users can also run `certonaut` as a regular unprivileged
user account. In this case you may need to adjust permissions of the `/etc/certonaut` directory though.

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

Simply use cargo to compile & install:

=== "All Features"

    ``` sh
    cargo install --all-features --git https://github.com/certonaut/certonaut.git --bin certonaut
    ```

=== "Lite"

    ``` sh
    cargo install --git https://github.com/certonaut/certonaut.git --bin certonaut
    ```

If everything is succesful, the installed `certonaut` binary should be in `~/.cargo/bin/certonaut` (which should also be in your path).

## Next steps

After having installed certonaut, head over to [usage](usage.md)