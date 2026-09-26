[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![Apache 2.0 License][license-shield]][license-url]

<br />
<div align="center">
  <h1 align="center">Paco BLAS</h1>

  <p align="center">
    Bindings oficiales de BLAS para Paco — un acelerador opcional para el matmul de pacolang/tensor a través del libblas del sistema
    <br />
    <a href="https://github.com/pacolang/paco"><strong>Explora el compilador paco »</strong></a>
    <br />
    <br />
    <a href="https://github.com/pacolang/blas/issues">Reportar un problema</a>
    ·
    <a href="https://github.com/pacolang/rfcs">Proponer una RFC</a>
  </p>
</div>

**Leer en:** [English](README.md) · [Português](README.pt-BR.md) · **Español**

> **Estado:** placeholder. Este repositorio está reservado para los
> bindings de BLAS, pero todavía no los contiene — ve
> [Sobre el Proyecto](#sobre-el-proyecto).

## Índice

<ol>
  <li><a href="#sobre-el-proyecto">Sobre el Proyecto</a></li>
  <li><a href="#primeros-pasos">Primeros Pasos</a>
    <ul>
      <li><a href="#requisitos-previos">Requisitos Previos</a></li>
      <li><a href="#instalación">Instalación</a></li>
    </ul>
  </li>
  <li><a href="#uso">Uso</a></li>
  <li><a href="#hoja-de-ruta">Hoja de Ruta</a></li>
  <li><a href="#contribuir">Contribuir</a></li>
  <li><a href="#licencia">Licencia</a></li>
  <li><a href="#contacto">Contacto</a></li>
</ol>

## Sobre el Proyecto

Este repositorio es el destino planeado para los bindings oficiales de
BLAS de Paco — un acelerador opcional que permite que el `matmul` de
[`pacolang/tensor`](https://github.com/pacolang/tensor) llame al
`libblas` del sistema en lugar de su propia implementación
predeterminada. **Todavía no han sido extraídos**. Por ahora, este
repositorio contiene solo este README y el archivo `LICENSE`; no hay
código aquí para instalar ni usar.

`stdlib::blas` (que define este binding hoy) todavía vive en
[`pacolang/paco`](https://github.com/pacolang/paco). Moverlo a este
repositorio está planeado, pero aún no se ha hecho. Ser opcional y
enlazado dinámicamente es exactamente por lo que este binding no
pertenece al `stdlib` ni a `pacolang/tensor` en sí — importarlo es lo
único que debería introducir enlazado dinámico en un binario de Paco
que, de otro modo, sería estático. El razonamiento detrás de separar
bibliotecas oficiales como esta del `stdlib` hacia sus propios
repositorios está registrado en la
[RFC 0030](https://github.com/pacolang/rfcs/blob/main/text/0030-repository-organization-and-stdlib-scope.md),
en [`pacolang/rfcs`](https://github.com/pacolang/rfcs).

## Primeros Pasos

### Requisitos Previos

Un toolchain `paco` funcional — consulta
[`pacolang/paco`](https://github.com/pacolang/paco) — y, cuando ocurra la
extracción, una instalación de BLAS en el sistema (por ejemplo OpenBLAS
o el BLAS de referencia) que provea `libblas` para que este paquete se
enlace contra ella.

### Instalación

Una vez que estos bindings hayan sido extraídos aquí y se marque una
versión con tag, serán instalables de la misma forma que cualquier
dependencia de Paco:

```sh
paco get github.com/pacolang/blas@<version>
```

**Esto todavía no funciona.** No se ha publicado ninguna versión de esta
biblioteca; el comando anterior documenta el flujo de trabajo previsto
para cuando ocurra la extracción, no algo que puedas ejecutar hoy.

## Uso

Todavía no hay código para usar. Cuando los bindings lleguen aquí,
activar el `matmul` de [`pacolang/tensor`](https://github.com/pacolang/tensor)
para usar el `libblas` del sistema se verá así:

```paco
use blas
```

Hasta entonces, este binding solo está disponible donde vive hoy, en
`stdlib::blas` de `pacolang/paco`, y ningún programa construido solo con
`pacolang/paco` se enlaza dinámicamente por su causa.

## Hoja de Ruta

- [ ] Extraer el binding de `libblas` de `stdlib::blas` de
      `pacolang/paco` hacia este repositorio, según la
      [RFC 0030](https://github.com/pacolang/rfcs/blob/main/text/0030-repository-organization-and-stdlib-scope.md),
      después de que el `matmul` de
      [`pacolang/tensor`](https://github.com/pacolang/tensor) tenga un
      punto de extensión estable para acelerar.
- [ ] Declarar un rango de versiones compatibles del compilador `paco` en
      `paco.mod`.
- [ ] Marcar la primera versión real con tag.

Consulta los [issues](https://github.com/pacolang/blas/issues) y
[milestones](https://github.com/pacolang/blas/milestones) de este
repositorio para el seguimiento del día a día.

## Contribuir

Este repositorio todavía no tiene código extraído, así que no hay una
API contra la cual enviar pull requests. Cualquier pregunta de diseño —
cómo debería exponerse el binding, cómo debería secuenciarse la
extracción — pertenece primero a una RFC en
[`pacolang/rfcs`](https://github.com/pacolang/rfcs).

Cuando el código llegue aquí, se aplica el flujo habitual:

1. Haz un fork del repositorio.
2. Crea tu rama de funcionalidad (`git checkout -b feat/my-feature`).
3. Haz commit de tus cambios y abre un pull request.

## Licencia

Distribuido bajo la Apache License, Version 2.0. Consulta
[`LICENSE`](LICENSE) para más información.

## Contacto

Enlace del proyecto: [https://github.com/pacolang/blas](https://github.com/pacolang/blas)

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
