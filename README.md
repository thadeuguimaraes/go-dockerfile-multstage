## Como Otimizar Imagens Docker para Produção

## O que é Multistage Build?

- Multistage Build é uma funcionalidade do Docker que permite criar várias etapas de construção em um único Dockerfile.
- Com o Multistage Build, é possível ter diferentes estágios de construção para compilar, empacotar e implantar a aplicação, resultando em uma imagem final mais enxuta e eficiente.

## Onde usar o Multistage Build?

- É particularmente útil em linguagens de programação como Go, onde é possível dividir o processo de compilação e empacotamento em estágios distintos.
- Recomenda-se seu uso em qualquer cenário onde seja necessário reduzir o tamanho da imagem Docker.

## Por que se preocupar com o tamanho da sua imagem Docker?

 - O tamanho da imagem Docker influencia diretamente no consumo de recursos do sistema hospedeiro, no desempenho e na eficiência do armazenamento e transferência de imagens.

## Quais as vantagens em ter uma imagem otimizada?

- Redução do tempo de implantação: imagens menores são transferidas e implantadas mais rapidamente.
- Eficiência de armazenamento: menor tamanho resulta em uso reduzido de espaço em disco.
- Maior segurança: menos componentes significa uma menor superfície de ataque.
- Menor exposição a vulnerabilidades, pois menos componentes estão presentes na imagem.


## O que será eliminado das imagens:

- Nas imagens resultantes do Multistage Build, serão eliminados os artefatos de compilação, dependências e quaisquer outros componentes não essenciais à execução da aplicação, resultando em imagens mais leves e eficientes.
- SDK (Software Development Kit) refere-se a um conjunto de ferramentas, bibliotecas e documentações que ajudam no desenvolvimento de software.

Como utilizar o Multistage Build na prática:

## Primeira Etapa (builder):

- FROM golang:1.21.0-alpine3.18 as builder: Define a primeira etapa do build multistage usando a imagem base do Golang versão 1.21.0 com Alpine Linux 3.18 como builder.
- WORKDIR /build: Define o diretório de trabalho como /build.
- COPY . .: Copia todos os arquivos do diretório local para o diretório de trabalho dentro do container.
- RUN go build -o webtest: Compila o código fonte Go presente no diretório de trabalho e cria um executável chamado webtest.

## Segunda Etapa (prod):

- FROM alpine:3.18 as prod: Inicia a segunda etapa do multistage build, utilizando a imagem base do Alpine Linux 3.18 como prod.
- WORKDIR /app: Define o diretório de trabalho como /app.
- COPY --from=builder /build/webtest .: Copia o executável webtest gerado na etapa anterior (builder) para o diretório de trabalho atual na nova imagem.
- CMD [ "./webtest" ]: Define o comando padrão a ser executado quando um container baseado nessa imagem for iniciado. Neste caso, executa o arquivo webtest.

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
