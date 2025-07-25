# Projeto de Consumo de APIs em Python

[![Open In Colab](https://colab.research.google.com/github/carolcerceau/API/blob/main/API.ipynb)](https://colab.research.google.com/github/carolcerceau/API/blob/main/API.ipynb)

Este projeto é um notebook Jupyter (Google Colab) que demonstra o consumo de diferentes APIs públicas em Python usando a biblioteca `requests`, além de realizar a visualização de dados com `pandas` e `matplotlib`.

---

## Visão Geral

O objetivo principal deste notebook é apresentar exemplos práticos de como interagir com APIs RESTful para obter dados variados, como informações de CEP e cotações de moedas. Além disso, o projeto mostra como processar esses dados e visualizá-los graficamente.

---

## Estrutura do Projeto

* `API.ipynb`: O notebook principal do Google Colab contendo o código Python para as consultas às APIs e visualização.

---

## Como Usar

Para executar este notebook:

1.  Clique no badge "Open In Colab" acima ou acesse o link direto: [https://colab.research.google.com/github/carolcerceau/API/blob/main/API.ipynb](https://colab.research.google.com/github/carolcerceau/API/blob/main/API.ipynb)
2.  O notebook será aberto no ambiente do Google Colab.
3.  Execute as células do notebook sequencialmente para ver as consultas e os resultados.

---

## Funcionalidades e Análise Realizada

O notebook executa as seguintes etapas e demonstrações:

1.  **Consulta de CEP (Awesome API)**:
    * Realiza uma consulta de CEP utilizando a [Awesome API](https://cep.awesomeapi.com.br/).
    * Exibe o **JSON** retornado pela API, que inclui detalhes como `cep`, `address_type`, `address_name`, `city`, `state`, `district`, entre outros.
    * Demonstra como acessar informações específicas do JSON, como `['city']`.

2.  **Verificação de Status de Resposta HTTP**:
    * Faz uma nova consulta de CEP e exibe o objeto de **resposta HTTP** (`res`).
    * Imprime o **código de status HTTP** (`res.status_code`), explicando os significados dos códigos (1xx - informação, 2xx - sucesso, 3xx - redirecionar, 4xx - erro cliente, 5xx - erro servidor).
    * Mostra uma verificação condicional (`if(res):`) para determinar se a requisição foi bem-sucedida.

3.  **Obtenção da Última Cotação de Moedas (Awesome API)**:
    * Consulta a [Awesome API de Economia](https://economia.awesomeapi.com.br/) para obter as últimas cotações de **Dólar (USD-BRL)**, **Euro (EUR-BRL)** e **Bitcoin (BTC-BRL)**.
    * Exibe o **texto bruto da resposta** (`res.text`) e, em seguida, demonstra como extrair o valor de compra (`bid`) do Dólar (`res.json()['USDBRL']['bid']`).

4.  **Consulta de Lista de CEPs (ViaCEP API)**:
    * Itera sobre uma lista de CEPs pré-definidos (`lista_ceps`).
    * Para cada CEP, realiza uma consulta à [API ViaCEP](https://viacep.com.br/).
    * Imprime o **CEP** e o **JSON completo** de cada resposta, ou uma mensagem de erro se a requisição não for bem-sucedida.

5.  **Histórico de Cotação do Dólar e Visualização Gráfica**:
    * Obtém o histórico de cotações do Dólar (USD-BRL) dos últimos 30 dias usando a Awesome API.
    * Converte a lista de dicionários (`cotacoes`) em um **DataFrame do pandas**.
    * Converte os valores de `bid` (compra) para numérico e os `timestamps` para o formato de data e hora.
    * Utiliza a biblioteca `matplotlib.pyplot` para **plotar um gráfico de linha** da cotação do Dólar ao longo dos últimos 30 dias, com rótulos para os eixos e rotação vertical para as datas.

---
