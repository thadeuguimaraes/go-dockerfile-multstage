## Como Otimizar Imagens Docker para Produção

Por que se preocupar com o tamanho da sua imagem Docker?

 - O tamanho da imagem Docker influencia diretamente no consumo de recursos do sistema hospedeiro, no desempenho e na eficiência do armazenamento e transferência de imagens.

## Quais as vantagens em ter uma imagem otimizada?

- Redução do tempo de implantação: imagens menores são transferidas e implantadas mais rapidamente.
- Eficiência de armazenamento: menor tamanho resulta em uso reduzido de espaço em disco.
- Maior segurança: menos componentes significa uma menor superfície de ataque.
- Menor exposição a vulnerabilidades, pois menos componentes estão presentes na imagem.
- 
## O que é Multistage Build?

- Multistage Build é uma funcionalidade do Docker que permite criar várias etapas de construção em um único Dockerfile.
- Com o Multistage Build, é possível ter diferentes estágios de construção para compilar, empacotar e implantar a aplicação, resultando em uma imagem final mais enxuta e eficiente.

## Onde usar o Multistage Build?

- É particularmente útil em linguagens de programação como Go, onde é possível dividir o processo de compilação e empacotamento em estágios distintos.
- Recomenda-se seu uso em qualquer cenário onde seja necessário reduzir o tamanho da imagem Docker.

## SDK:

- SDK refere-se a um conjunto de ferramentas, bibliotecas e documentações que ajudam no desenvolvimento de software.

## O que será eliminado das imagens:

- Nas imagens resultantes do Multistage Build, serão eliminados os artefatos de compilação, dependências e quaisquer outros componentes não essenciais à execução da aplicação, resultando em imagens mais leves e eficientes.

Como utilizar o Multistage Build na prática:

Resultado:

O primeiro estágio compila a aplicação Go e o segundo cria uma imagem final contendo apenas o binário necessário para executar a aplicação.

```bash
docker build -t devopsguimaraes/web-test:simples .
```
```bash
docker pull  golang:1.21.0-alpine3.18
```
```bash
docker build -t devopsguimaraes/web-test:multistage .
```
```bash
docker container run -d -p 8080:8080 devopsguimaraes/web-test:multistage
```
```bash
docker build -t devopsguimaraes/web-test:target --target builder .
```
