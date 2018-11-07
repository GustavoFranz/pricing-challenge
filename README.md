# Geospatial pricing software
Software para cálculo de valores a receber com base em informações geográficas.

## Contexto
Seu cliente, uma grande consultoria agrária do estado do Paraná, é responsável por prestar serviços para diversos agricultores da região e gera boletos referentes aos serviços prestados no mês e mais uma taxa de manutenção proporcional ao tamanho da fazenda do agricultor. Porém, este processo é realizado manualmente por funcionários da consultoria e, em alguns meses, pode-se notar inconsistências nos serviços prestados e no valor cobrado. Para resolver a situação, seu cliente deseja automatizar o cálculo de precificação de seus serviços.

## Precificação

Hoje, a precificação dos serviços da consultoria são como segue:

1. Taxa de manutenção
    - Se a fazenda tiver a área inferior a 50 ha: R$0,25 por hectare;
    - Se a fazenda tiver a área entre 50 e 150 ha: R$0,22 por hectare;
    - Se a fazenda tiver a área superior a 150 ha: R$0,20 por hectare;
2. Análise de qualidade de solo
    - R$279,90 por ponto de análise;
    - Caso a mesma fazenda tenha mais de 10 pontos de monitoramento, o valor de cada ponto sai por R$249,90;
3. Contagem de pragas
    - R$399,90 por ponto monitorado;
    - Caso a mesma fazenda tenha mais de 5 pontos de monitoramento, o valor de cada ponto sai por R$379,90;

## Fonte de dados
A pasta `data/` contém dois arquivos de formato `csv`. O primeiro, `fazendas.csv` contém a lista de todas as fazendas que são clientes da consultoria agrária, identificadas por um identificador único, um nome e um GeoJSON do polígno que representa os limites da fazenda. Já no arquivo `servicos.csv`, você irá encontrar a lista de serviços prestados no último mês e a geolocalização de onde o serviço foi realizado.

## Saída de dados
Espera-se que o programa apresente como saída um arquivo no formato `csv` contendo as seguintes colunas:

- #Id da fazenda
- Nome da fazenda
- Taxa de manutenção
- Valor dos serviços
- Preço a cobrar

Onde cada linha do arquivo represente uma fazenda distinta.

## Referências

- [JTS Topology Suite](https://github.com/locationtech/jts)
- Clean Code: A Handbook of Agile Software Craftsmanship, Robert C. Martin, 2008.

## Notas

- O software deve ser desenvolvido na linguagem Java e você pode fazer uso de qualquer biblioteca disponível;
- A exatidão do software é importante, porém, a qualidade do produto e a facilidade de manutenção também devem ser levadas em consideração;
- Testes automatizados não são obrigatórios, porém, aumentam a qualidade e confiabilidade de sua entrega;