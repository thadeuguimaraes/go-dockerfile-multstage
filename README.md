# go-dockerfile-multstage

Introdução:
Olá! Vamos entender como usar o Multistage Build do Docker para criar imagens otimizadas para aplicações Go.

Por que se preocupar com o tamanho da imagem Docker?

O tamanho da imagem Docker afeta o armazenamento, a transferência e o tempo de implantação.
Imagens menores têm menos impacto no armazenamento, consomem menos largura de banda e têm implantação mais rápida.
O que é Multistage Build?

Multistage Build é uma funcionalidade do Docker que permite criar etapas sequenciais em um único Dockerfile.
É usado para compilar, testar e construir a aplicação em estágios separados, reduzindo o tamanho final da imagem.
Vantagens de uma imagem otimizada:

Redução significativa do tamanho final, eliminando dependências desnecessárias.
Menor superfície de ataque, aumentando a segurança.
Implantação mais rápida devido ao menor volume de dados.
Onde usar o Multistage Build:

Ideal para linguagens de programação compiladas, como Go.
Projetos com várias etapas de compilação, teste e empacotamento.
Como utilizar o Multistage Build na prática:

Resultados:

Imagem otimizada usando o segundo estágio "FROM scratch", contendo apenas o binário executável.
Redução significativa do tamanho comparado a uma imagem não otimizada.
SDK:

Utilize o SDK oficial do Docker ou o Docker Engine para construir e executar as imagens.
O que será eliminado das imagens:

As imagens otimizadas eliminarão dependências desnecessárias, bibliotecas e artefatos intermediários, mantendo apenas o binário executável.
Espero que este script ajude a entender como usar o Multistage Build no Docker para criar imagens otimizadas em Go, eliminando elementos desnecessários e reduzindo o tamanho final da imagem.

Por que se preocupar com o tamanho da imagem Docker?

O tamanho da imagem Docker pode afetar a velocidade de implantação, consumo de armazenamento e largura de banda.
Quais as vantagens de ter uma imagem otimizada?

Redução do tamanho da imagem, facilitando a distribuição e o armazenamento.
Menor ataque à superfície devido à eliminação de componentes desnecessários.
Implantação mais rápida devido a um menor volume de dados a ser transferido.
O que é Multistage Build?

O Multistage Build é uma funcionalidade do Docker que permite definir várias etapas de construção em um único Dockerfile.
Ele ajuda a separar as fases de construção, teste e empacotamento, reduzindo o tamanho final da imagem.
Onde usar o Multistage Build?

Ideal para linguagens compiladas, como Go, onde existem várias etapas de compilação e empacotamento.
Como utilizar o Multistage Build na prática:

Copy code
```bash
docker build -t devopsguimaraes/web-test:simples .
```
Resultados:

A imagem otimizada, usando o segundo estágio "FROM scratch", conterá apenas o binário executável.
Comparativamente, a imagem não otimizada terá maior tamanho, incluindo dependências e artefatos de compilação.
SDK:

O SDK (Software Development Kit) é um conjunto de ferramentas, bibliotecas e documentações para desenvolvedores.
O que será eliminado das imagens:

Nas imagens otimizadas, as dependências e artefatos de compilação são eliminados, mantendo apenas o binário executável final.
Este script destaca o uso do Multistage Build para criar imagens Docker otimizadas em Go, demonstrando como reduzir o tamanho da imagem, focando na eliminação de componentes desnecessários e na melhoria da eficiência da implantação.
