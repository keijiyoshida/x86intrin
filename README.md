# x86intrin
x86 intrinsics for rust

[![Crates.io Status](https://img.shields.io/crates/v/x86intrin.svg)](https://crates.io/crates/x86intrin)
[![Build Status](https://travis-ci.org/mayah/x86intrin.svg?branch=master)](http://travis-ci.org/mayah/x86intrin)

This crate implements C-like x86 intrinsics. The function and type names are
the same as what Intel uses (removing prefix underscore; e.g. `__m128i -> m128i`,
`_mm_set_epi32 -> mm_set_epi32`).

I actually need various integer SIMD arithmetics, so such functions will
be implemeneted with priority.

# Current Status

Currently most of SSE, SSE2, SSE3, SSSE3, SSE4.1, SSE4.2, AVX, and AVX2 are implemented.
Some of the functions cannot be implemented since rust is not exposing necessary
functions.

After all done, I'd like to contribute to rust libraries to support missing functions.

# Note

You need *nightly* channel, since this crate uses unstable features.

To build with `cargo`, you need to set `target-cpu` or `target-feature` in `RUSTFLAGS`.

For example:
```
$ RUSTFLAGS="-C target-cpu=native" cargo build
$ RUSTFLAGS="-C target-feature=+sse3" cargo build
```
