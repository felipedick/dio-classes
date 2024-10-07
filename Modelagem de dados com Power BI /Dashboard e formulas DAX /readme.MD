# Desafio de Projeto: Modelo Star Schema com Financial Sample

Este projeto faz parte de um desafio de criação de um modelo de dados baseado em **Star Schema** utilizando a tabela única *Financial Sample*. O objetivo é transformar a tabela original em uma estrutura de tabelas de dimensão e fato, organizadas de maneira eficiente para facilitar a análise de dados.

## Objetivo
Criar tabelas de dimensão e fato a partir de uma tabela única utilizando Power BI. A partir disso, implementar um modelo de dados relacional com base no esquema em estrela (Star Schema).

## Tabelas Criadas

### 1. **Financials_origem (modo oculto - backup)**
   - Backup da tabela original para referência e segurança.

### 2. **D_Produtos**
   - **ID_produto**: Chave primária da tabela de produtos.
   - **Produto**: Nome do produto.
   - **Média de Unidades Vendidas**: Média de unidades vendidas por produto.
   - **Médias do valor de vendas**: Média dos valores de venda.
   - **Mediana do valor de vendas**: Mediana dos valores de venda.
   - **Valor máximo de Venda**: Valor máximo de venda por produto.
   - **Valor mínimo de Venda**: Valor mínimo de venda por produto.

### 3. **D_Produtos_Detalhes**
   - **ID_produto**: Chave primária da tabela de detalhes de produto.
   - **Discount Band**: Faixa de desconto aplicada.
   - **Sale Price**: Preço de venda.
   - **Units Sold**: Unidades vendidas.
   - **Manufacturing Price**: Preço de fabricação.

### 4. **D_Descontos**
   - **ID_produto**: Chave primária.
   - **Discount**: Valor do desconto aplicado.
   - **Discount Band**: Faixa de desconto.

### 5. **D_Detalhes**
   - Detalhes adicionais de vendas não contemplados em outras tabelas.

### 6. **D_Calendário**
   - Criada através da função DAX `CALENDAR()` para gerenciamento de datas.

### 7. **F_Vendas**
   - **SK_ID**: Chave substituta.
   - **ID_Produto**: Chave estrangeira para produtos.
   - **Produto**: Nome do produto.
   - **Units Sold**: Unidades vendidas.
   - **Sales Price**: Preço de venda.
   - **Discount Band**: Faixa de desconto.
   - **Segment**: Segmento de mercado.
   - **Country**: País.
   - **Salers**: Vendedores.
   - **Profit**: Lucro.
   - **Date**: Data da venda.

## Funções DAX Utilizadas

- **CALENDAR()**: Utilizada para criar a tabela `D_Calendário` e gerenciar datas no modelo.
- **Médias e Medianas**: Funções de agregação para calcular métricas como média e mediana nas tabelas de dimensão.

## Processo de Construção do Diagrama

1. **Preparação dos Dados**: A tabela original *Financial Sample* foi copiada para criar a tabela *Financials_origem* para referência futura.
2. **Criação de Tabelas Dimensão e Fato**: A partir da tabela original, criamos tabelas de dimensão que armazenam informações como produtos, descontos e detalhes, enquanto a tabela fato concentra dados de vendas.
3. **Relacionamentos**: Definimos os relacionamentos entre as tabelas, conforme a metodologia do Star Schema, para garantir a eficiência das consultas.
4. **Organização das Colunas**: Colunas reorganizadas e renomeadas conforme o contexto e necessidade do modelo.
5. **Implementação de Funções DAX**: Funções DAX aplicadas para gerar colunas calculadas e métricas agregadas.

## Imagem do Esquema em Estrela
![Star Schema](link-da-imagem-aqui)

## Arquivo PBIX
O arquivo `.pbix` com a solução completa está disponível neste repositório.

## Conclusão

Este projeto implementa um modelo Star Schema eficaz para análise de dados financeiros. Utilizando Power BI e funções DAX, as informações foram organizadas em tabelas de dimensão e fato, proporcionando um modelo otimizado para consultas e relatórios.

---
