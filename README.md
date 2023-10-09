# ETL dos Índices Financeiros

## Descrição
Este script realiza ETL (Extract, Transform, Load) para índices financeiros, utilizando várias fontes de dados, como a API do Banco Central do Brasil (BACEN), web scraping dos sites da ANBIMA e B3, e a biblioteca Yahoo Finance.

## Fontes de Dados
- **API do BACEN:** Os dados são extraídos através da URL `http://api.bcb.gov.br/dados/serie/bcdata.sgs.{codigo}/dados?formato=csv&dataInicial={data_inicial}&dataFinal={data_final}`, onde `{codigo}` é o código da série e `{data_inicial}` e `{data_final}` definem o intervalo de datas. Os códigos das séries podem ser encontrados [aqui](https://www3.bcb.gov.br/sgspub/localizarseries/localizarSeries.do?method=prepararTelaLocalizarSeries).

- **Web Scraping ANBIMA:** Os dados são extraídos do [site da ANBIMA](https://data.anbima.com.br/indices/consulta/ima/resultados-diarios/ima-geral), e o código do índice na URL é alterado conforme necessário. O arquivo XLSX contendo os dados pode ser encontrado [neste link](https://adata-precos-prod.s3.amazonaws.com/arquivos/indices-historico/IMAGERAL-HISTORICO.xls).

- **Web Scraping B3:** Os dados são extraídos do [site da B3](https://www.b3.com.br/pt_br/market-data-e-indices/indices/indices-de-segmentos-e-setoriais/indice-dividendos-idiv-estatisticas-historicas.htm). O endpoint encontrado através da inspeção da página é utilizado para extração de dados.

- **Yahoo Finance:** A biblioteca Yahoo Finance é utilizada para extrair dados de alguns índices.

## Requisitos
- Python
- Bibliotecas Python: pandas, datetime, requests, yfinance, plotly, openpyxl

## Como Usar
1. Instale as bibliotecas Python listadas em "Requisitos".
2. Execute o script usando um interpretador Python.

## Funções
- `plot_line(df, x_col='data', y_col='rent', title="Line Plot", x_label="Date", y_label="Rent")`: Esta função cria e exibe um gráfico de linha com os dados fornecidos.

## Objetivo
O script foi criado com o objetivo de realizar ETL em índices financeiros para uso em outros projetos.

## Autor
Inserir nome do autor aqui

## Licença
Este projeto está licenciado sob a Licença MIT - veja o arquivo [LICENSE.md](LICENSE.md) para detalhes.
