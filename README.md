## Como Otimizar Imagens Docker para Produção

Por que se preocupar com o tamanho da sua imagem Docker?

O tamanho da imagem Docker influencia diretamente no consumo de recursos do sistema hospedeiro, no desempenho e na eficiência do armazenamento e transferência de imagens.
Quais as vantagens em ter uma imagem otimizada?

Redução do tempo de implantação: imagens menores são transferidas e implantadas mais rapidamente.
Eficiência de armazenamento: menor tamanho resulta em uso reduzido de espaço em disco.
Maior segurança: menos componentes significa uma menor superfície de ataque.
O que é Multistage Build?

Multistage Build é uma funcionalidade do Docker que permite criar várias etapas de construção em um único Dockerfile.
Com o Multistage Build, é possível ter diferentes estágios de construção para compilar, empacotar e implantar a aplicação, resultando em uma imagem final mais enxuta e eficiente.
Onde usar o Multistage Build?

É particularmente útil em linguagens de programação como Go, onde é possível dividir o processo de compilação e empacotamento em estágios distintos.
Recomenda-se seu uso em qualquer cenário onde seja necessário reduzir o tamanho da imagem Docker.

Como utilizar o Multistage Build na prática:

Resultado:

O primeiro estágio compila a aplicação Go e o segundo cria uma imagem final contendo apenas o binário necessário para executar a aplicação.
