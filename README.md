# Geospatial pricing software
Software para cálculo de valores a receber com base em informações geográficas.

## Contexto
Seu cliente, uma grande consultoria agrária do estado do Paraná, é responsável por prestar serviços para diversos agricultores da região e gera boletos referentes aos serviços prestados no mês e mais uma taxa de manutenção proporcional ao tamanho da fazenda do agricultor. Porém, este processo é realizado manualmente por funcionários da consultoria e, em alguns meses, pode-se notar inconsistências nos serviços prestados e no valor cobrado. Para resolver a situação, seu cliente deseja automatizar o cálculo de precificação de seus serviços e possa auditar o resultado utilizando um mapa interativo.

## Precificação

Hoje, a precificação dos serviços da consultoria são como segue:

1. Taxa de manutenção
    - Se a fazenda tiver a área inferior a 50 ha: R$1,25 por hectare;
    - Se a fazenda tiver a área entre 50 e 1.000 ha: R$1,15 por hectare;
    - Se a fazenda tiver a área superior a 1.000 ha: R$1,02 por hectare;
2. Análise de qualidade de solo
    - R$279,90 por ponto de análise;
    - Caso a mesma fazenda tenha mais de 10 pontos de monitoramento, o valor de cada ponto sai por R$249,90;
3. Contagem de pragas
    - R$399,90 por ponto monitorado;
    - Caso a mesma fazenda tenha mais de 5 pontos de monitoramento, o valor de cada ponto sai por R$379,90;

## Fonte de dados
A pasta `input/` contém dois arquivos de formato `csv`. O primeiro, `fazendas.csv` contém a lista de todas as fazendas que são clientes da consultoria agrária, identificadas por um identificador único, um nome e um GeoJSON do polígno que representa os limites da fazenda. Já no arquivo `servicos.csv`, você irá encontrar a lista de serviços prestados no último mês e a geolocalização de onde o serviço foi realizado.

## Solução esperada
Espera-se que o resultado deste projeto gere dois entregáveis:
1. Uma API Restful que consome os dados do arquivo `csv` e retorne os dados necessários para a renderização do mapa;
2. Um mapa contendo o desenho do contorno de todas as fazendas processadas e, ao clicar em uma fazenda, deve-se exibir um tooltip contendo o nome da fazenda selecionada e o valor a ser cobrado pelos serviços prestados à fazenda.

Exemplo de resultado esperado:
![Exemplo de mapa](https://raw.githubusercontent.com/mathnogueira/pricing-challenge/development/pictures/map.png)

## Referências

As referências abaixo serão úteis para sanar dúvidas simples sobre as principais tecnologias que podem ser utilizadas neste teste. Espera-se que você consulte mais materiais ao decorrer do desenvolvimento do projeto para conseguir sanar dúvidas mais complexas.

- [JTS Topology Suite](https://github.com/locationtech/jts)
- [JTS basics](http://docs.geotools.org/latest/userguide/library/jts/index.html)
- [Leaflet](https://leafletjs.com/)
- [Spring Boot basics](https://spring.io/guides/gs/spring-boot/)
- [RESTful Spring Boot](https://spring.io/guides/gs/rest-service/)

## Notas

- O software deve ser desenvolvido na linguagem Java e você pode fazer uso de qualquer biblioteca disponível;
- A exatidão do software é importante, porém, a qualidade do produto e a facilidade de manutenção também devem ser levadas em consideração;
- Seu projeto deve estar hospedado no GitHub em modo público para que possamos visualizar sua solução.