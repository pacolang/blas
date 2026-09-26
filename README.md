[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![Apache 2.0 License][license-shield]][license-url]

<br />
<div align="center">
  <h1 align="center">Paco BLAS</h1>

  <p align="center">
    Official BLAS bindings for Paco — an optional accelerator for pacolang/math's Matrix multiply via the system libblas
    <br />
    <a href="https://github.com/pacolang/paco"><strong>Explore the paco compiler »</strong></a>
    <br />
    <br />
    <a href="https://github.com/pacolang/blas/issues">Report an issue</a>
    ·
    <a href="https://github.com/pacolang/rfcs">Propose an RFC</a>
  </p>
</div>

**Read this in:** **English** · [Português](README.pt-BR.md) · [Español](README.es.md)

> **Status:** placeholder. This repository is reserved for the BLAS
> bindings but does not contain them yet — see [About](#about-the-project).

## Table of Contents

<ol>
  <li><a href="#about-the-project">About The Project</a></li>
  <li><a href="#getting-started">Getting Started</a>
    <ul>
      <li><a href="#prerequisites">Prerequisites</a></li>
      <li><a href="#installation">Installation</a></li>
    </ul>
  </li>
  <li><a href="#usage">Usage</a></li>
  <li><a href="#roadmap">Roadmap</a></li>
  <li><a href="#contributing">Contributing</a></li>
  <li><a href="#license">License</a></li>
  <li><a href="#contact">Contact</a></li>
</ol>

## About The Project

This repository is the designated home for Paco's official BLAS
bindings — an optional accelerator that lets
[`pacolang/math`](https://github.com/pacolang/math)'s `Matrix::matmul`
call into the system `libblas` instead of its own default
implementation, using [`pacolang/tensor`](https://github.com/pacolang/tensor)'s
`ShapeError` for its error type. It has **not been extracted yet**. Right
now this repository holds only this README and the `LICENSE` file; there
is no code here to install or use.

`stdlib::blas` (which defines this binding today) still lives in
[`pacolang/paco`](https://github.com/pacolang/paco). Moving it out to this
repository is planned but not yet done. Being optional and dynamically
linked is exactly why this binding does not belong in `stdlib` or in
`pacolang/math` itself — importing it is the one thing that should ever
pull dynamic linking into an otherwise static Paco binary. The reasoning
behind splitting official libraries like this one out of `stdlib` and into
their own repositories is recorded in
[RFC 0030](https://github.com/pacolang/rfcs/blob/main/text/0030-repository-organization-and-stdlib-scope.md),
in [`pacolang/rfcs`](https://github.com/pacolang/rfcs).

## Getting Started

### Prerequisites

A working `paco` toolchain — see [`pacolang/paco`](https://github.com/pacolang/paco)
— and, once extraction lands, a system BLAS installation (for example
OpenBLAS or reference BLAS) providing `libblas` for this crate to link
against.

### Installation

Once these bindings have been extracted here and a version is tagged,
they will be installable the same way any Paco dependency is:

```sh
paco get github.com/pacolang/blas@<version>
```

**This does not work yet.** No version of this library has been
published; the command above documents the intended workflow for when
extraction lands, not something you can run today.

## Usage

There is no code to use yet. Once the bindings land here, opting
[`pacolang/math`](https://github.com/pacolang/math)'s `Matrix::matmul` into
the system `libblas` will look like:

```paco
use blas
```

Until then, this binding is only available where it lives today, in
`pacolang/paco`'s `stdlib::blas`, and no program built with `pacolang/paco`
alone links dynamically because of it.

## Roadmap

- [ ] Extract the `libblas` binding from `pacolang/paco`'s `stdlib::blas`
      into this repository, per
      [RFC 0030](https://github.com/pacolang/rfcs/blob/main/text/0030-repository-organization-and-stdlib-scope.md),
      after [`pacolang/math`](https://github.com/pacolang/math)'s
      `Matrix::matmul` has a stable extension point to accelerate.
- [ ] Declare a supported `paco` compiler-version range in `paco.mod`.
- [ ] Tag the first real release.

See this repository's [issues](https://github.com/pacolang/blas/issues)
and [milestones](https://github.com/pacolang/blas/milestones) for
day-to-day tracking.

## Contributing

This repository has no extracted code yet, so there isn't an API to send
pull requests against. Any design question — how the binding should be
exposed, how extraction should be sequenced — belongs in an RFC at
[`pacolang/rfcs`](https://github.com/pacolang/rfcs) first.

Once code lands here, the usual flow applies:

1. Fork the repository.
2. Create your feature branch (`git checkout -b feat/my-feature`).
3. Commit your changes and open a pull request.

## License

Distributed under the Apache License, Version 2.0. See [`LICENSE`](LICENSE)
for more information.

## Contact

Project Link: [https://github.com/pacolang/blas](https://github.com/pacolang/blas)

[contributors-shield]: https://img.shields.io/github/contributors/pacolang/blas.svg?style=for-the-badge
[contributors-url]: https://github.com/pacolang/blas/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/pacolang/blas.svg?style=for-the-badge
[forks-url]: https://github.com/pacolang/blas/network/members
[stars-shield]: https://img.shields.io/github/stars/pacolang/blas.svg?style=for-the-badge
[stars-url]: https://github.com/pacolang/blas/stargazers
[issues-shield]: https://img.shields.io/github/issues/pacolang/blas.svg?style=for-the-badge
[issues-url]: https://github.com/pacolang/blas/issues
[license-shield]: https://img.shields.io/github/license/pacolang/blas.svg?style=for-the-badge
[license-url]: https://github.com/pacolang/blas/blob/main/LICENSE
