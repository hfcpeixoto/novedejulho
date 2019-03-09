<p align="center"><img src="https://media.giphy.com/media/moN59IdquTB0xE0g5c/giphy.gif" width="100"></p>


# __Nove de Julho__

[![Maintainability](https://api.codeclimate.com/v1/badges/dc4a0d2281a965d5dfd6/maintainability)](https://codeclimate.com/github/rodolfo-viana/novedejulho/maintainability)
[![Build Status](https://travis-ci.org/rodolfo-viana/novedejulho.svg?branch=master)](https://travis-ci.org/rodolfo-viana/novedejulho)
[![codecov](https://img.shields.io/codecov/c/github/rodolfo-viana/novedejulho.svg)](https://codecov.io/gh/rodolfo-viana/novedejulho)<br>
[![GitHub release](https://img.shields.io/github/release/rodolfo-viana/novedejulho.svg)](https://github.com/rodolfo-viana/novedejulho/releases/)
[![Code size](https://img.shields.io/github/languages/code-size/rodolfo-viana/novedejulho.svg)](https://github.com/rodolfo-viana/novedejulho/releases/)
[![Feito com amor](https://img.shields.io/badge/made%20with-%3C3-red.svg)](https://www.youtube.com/watch?v=OKTRc7x-zCM)

> Criação de [rodolfo-viana](https://github.com/rodolfo-viana)<br>
> Colaborações de [cuducos](https://github.com/cuducos), [jtemporal](https://github.com/jtemporal) e [Vnicius](https://github.com/Vnicius)<br>
> Desenvolvimento desde janeiro de 2019

Nove de Julho é um projeto open-source de ativismo cívico com foco na Assembleia Legislativa do Estado de São Paulo.

Seu objetivo é agregar e formatar conjuntos de dados da Alesp, como gastos na cota parlamentar, proposições apresentadas, leis aprovadas, presenças em sessões, andamento de comissões, lista de funcionários, salários, entre outros.

### Fonte dos dados

Os dados são coletados diretamente da Alesp por meio do [Portal dos Dados Abertos](https://www.al.sp.gov.br/dados-abertos/) ou, quando não disponíveis no portal, por meio de raspagem do site oficial da assembleia.

Conjuntos referentes aos deputados durante campanhas eleitorais são coletados do [Repositório de Dados Eleitorais](http://www.tse.jus.br/eleicoes/estatisticas/repositorio-de-dados-eleitorais-1/repositorio-de-dados-eleitorais), do TSE.

### Conteúdo

`novedejulho.py` aciona mais de duas dezenas de scripts que fazem o download de dados como gastos feitos via verba de gabinete, salários dos servidores, presenças dos deputados em comissões, projetos apresentados etc.

![Screenshot](https://i.imgur.com/UCHsXgx.png)

Pelo começo do nome dos arquivos é possível saber a qual categoria pertence cada script:

- `cands` para dados dos deputados quando candidatos nas eleições de 2014 e 2018 (candidatos e bens declarados)
- `coms` para dados de comissões (votações, sessões, presenças etc.)
- `deps` para dados de deputados (bases eleitorais, áreas de atuação, gastos na cota etc.)
- `docs` para dados de documentos (projetos de lei, autores, pareceres etc.)
- `legs` para dados de legislação (normas, anotações, temas etc.)
- `servs` para dados de servidores (lotações, cargos, salários etc.)

Alguns desses scripts terminam com `indice` no nome. Isso indica que os dados raspados por meio deles servem como `foreign keys` em agregações.

Todos os dados são salvos em arquivos `.csv` (para ler em Excel ou LibreOffice Calc) e `.xz` (para usar com Pandas). Também são agregados em um banco de dados `.db` (para acessar com SQL).

Em 8 de março de 2019, `novedejulho.py` baixou 67 arquivos, sendo:

- 33 arquivos `.csv`, com tamanho total de ~339 Mb
- 33 arquivos `.xz`, com tamanho total de ~27 Mb
- 1 arquivo `.db`, com tamanho total de ~374 Mb

Outros scripts estão em produção, como para baixar contratos firmados pela Alesp e processos agregados no Tribunal de Justiça de São Paulo.

### Como usar

__Não é preciso ter experiência com qualquer linguagem de programação para usar os scripts.__ Basta seguir as instruções detalhadas [aqui](https://github.com/rodolfo-viana/novedejulho/blob/master/MANUAL_DE_USO.md).

Caso você tenha algum conhecimento de Python, basta clonar este repositório...

```
$ git clone https://github.com/rodolfo-viana/novedejulho.git
```

...e instalar as bibliotecas necessárias na pasta do projeto.

```
$ cd novedejulho
$ pip install -r requirements.txt
```

### Como colaborar

Você pode ajudar o Nove de Julho a ser melhor, mesmo que não saiba programar. [Clique aqui](https://github.com/rodolfo-viana/novedejulho/blob/master/CONTRIBUTING.md) para saber como contribuir.

### Licença MIT

Copyright (c) 2019 Rodolfo Viana
