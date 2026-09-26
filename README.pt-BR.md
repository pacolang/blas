[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![Apache 2.0 License][license-shield]][license-url]

<br />
<div align="center">
  <h1 align="center">Paco BLAS</h1>

  <p align="center">
    Bindings oficiais de BLAS para o Paco — um acelerador opcional para o matmul do pacolang/tensor via o libblas do sistema
    <br />
    <a href="https://github.com/pacolang/paco"><strong>Conheça o compilador paco »</strong></a>
    <br />
    <br />
    <a href="https://github.com/pacolang/blas/issues">Relatar um problema</a>
    ·
    <a href="https://github.com/pacolang/rfcs">Propor uma RFC</a>
  </p>
</div>

**Leia em:** [English](README.md) · **Português** · [Español](README.es.md)

> **Status:** placeholder. Este repositório está reservado para os
> bindings de BLAS, mas ainda não os contém — veja
> [Sobre o Projeto](#sobre-o-projeto).

## Índice

<ol>
  <li><a href="#sobre-o-projeto">Sobre o Projeto</a></li>
  <li><a href="#começando">Começando</a>
    <ul>
      <li><a href="#pré-requisitos">Pré-requisitos</a></li>
      <li><a href="#instalação">Instalação</a></li>
    </ul>
  </li>
  <li><a href="#uso">Uso</a></li>
  <li><a href="#roadmap">Roadmap</a></li>
  <li><a href="#contribuindo">Contribuindo</a></li>
  <li><a href="#licença">Licença</a></li>
  <li><a href="#contato">Contato</a></li>
</ol>

## Sobre o Projeto

Este repositório é o destino planejado para os bindings oficiais de BLAS
do Paco — um acelerador opcional que permite que o `matmul` do
[`pacolang/tensor`](https://github.com/pacolang/tensor) chame o `libblas`
do sistema em vez de sua própria implementação padrão. Eles **ainda não
foram extraídos**. Por enquanto, este repositório contém apenas este
README e o arquivo `LICENSE`; não há código aqui para instalar ou usar.

`stdlib::blas` (que define esse binding hoje) ainda vive em
[`pacolang/paco`](https://github.com/pacolang/paco). Movê-lo para este
repositório está planejado, mas ainda não foi feito. Ser opcional e
vinculado dinamicamente é exatamente por isso que esse binding não
pertence ao `stdlib` nem ao próprio `pacolang/tensor` — importá-lo é a
única coisa que deveria trazer vinculação dinâmica para um binário Paco
que, de outra forma, seria estático. O raciocínio por trás de separar
bibliotecas oficiais como esta do `stdlib` para seus próprios
repositórios está registrado na
[RFC 0030](https://github.com/pacolang/rfcs/blob/main/text/0030-repository-organization-and-stdlib-scope.md),
em [`pacolang/rfcs`](https://github.com/pacolang/rfcs).

## Começando

### Pré-requisitos

Um toolchain `paco` funcional — veja
[`pacolang/paco`](https://github.com/pacolang/paco) — e, quando a
extração acontecer, uma instalação de BLAS no sistema (por exemplo
OpenBLAS ou o BLAS de referência) fornecendo o `libblas` para este pacote
se vincular.

### Instalação

Uma vez que estes bindings tenham sido extraídos para cá e uma versão
seja marcada com tag, eles serão instaláveis da mesma forma que qualquer
dependência do Paco:

```sh
paco get github.com/pacolang/blas@<version>
```

**Isso ainda não funciona.** Nenhuma versão desta biblioteca foi
publicada; o comando acima documenta o fluxo de trabalho pretendido para
quando a extração acontecer, não algo que você pode executar hoje.

## Uso

Ainda não há código para usar. Quando os bindings chegarem aqui, ativar
o `matmul` do [`pacolang/tensor`](https://github.com/pacolang/tensor)
para usar o `libblas` do sistema vai se parecer com:

```paco
use blas
```

Até lá, esse binding só está disponível onde vive hoje, em `stdlib::blas`
do `pacolang/paco`, e nenhum programa construído apenas com o
`pacolang/paco` se vincula dinamicamente por causa dele.

## Roadmap

- [ ] Extrair o binding de `libblas` de `stdlib::blas` do `pacolang/paco`
      para este repositório, seguindo a
      [RFC 0030](https://github.com/pacolang/rfcs/blob/main/text/0030-repository-organization-and-stdlib-scope.md),
      depois que o `matmul` do
      [`pacolang/tensor`](https://github.com/pacolang/tensor) tiver um
      ponto de extensão estável para acelerar.
- [ ] Declarar uma faixa de versões suportadas do compilador `paco` no
      `paco.mod`.
- [ ] Marcar a primeira versão real com tag.

Veja os [issues](https://github.com/pacolang/blas/issues) e
[milestones](https://github.com/pacolang/blas/milestones) deste
repositório para o acompanhamento do dia a dia.

## Contribuindo

Este repositório ainda não tem código extraído, então não há uma API
para enviar pull requests. Qualquer questão de design — como o binding
deve ser exposto, como a extração deve ser sequenciada — pertence
primeiro a uma RFC em [`pacolang/rfcs`](https://github.com/pacolang/rfcs).

Quando o código chegar aqui, o fluxo de sempre se aplica:

1. Faça um fork do repositório.
2. Crie sua branch de feature (`git checkout -b feat/my-feature`).
3. Faça commit das suas alterações e abra um pull request.

## Licença

Distribuído sob a Apache License, Version 2.0. Veja [`LICENSE`](LICENSE)
para mais informações.

## Contato

Link do projeto: [https://github.com/pacolang/blas](https://github.com/pacolang/blas)

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
