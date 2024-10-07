# Desafio de Projeto: Modelo Star Schema com Financial Sample

Este projeto faz parte de um desafio de criação de um modelo de dados baseado em **Star Schema** utilizando a tabela única *Financial Sample*. O objetivo é transformar a tabela original em uma estrutura de tabelas de dimensão e fato, organizadas de maneira eficiente para facilitar a análise de dados.

## Objetivo
Criar tabelas de dimensão e fato a partir de uma tabela única utilizando Power BI. A partir disso, implementar um modelo de dados relacional com base no esquema em estrela (Star Schema).

## Resultados resumidos
- Criado modelo Star Schema conforme figura abaixo.

![Star Schema](./Images/0.%20Modelo%20Star%20Schema.PNG)


-Realizado criação de 3 Funções DAX: CALENDARAUTO, Lucro e Vendas Acumuladas

-Realizado alterações vs desafio proposto
   - Criado tabela D_Descontos referenciando nível (nenhum, baixo, médio e alto), conforme o desconto percentual
   - Criado tabela D_Manufacturing_Price referenciando custo de manufatura de acordo com o produto da venda
   - Tabela D_Produtos_Detalhes criada mas não utilizada devido a baixa eficiência da mesma em comparação com utilização direto das variáveis na tabela fato

## Tabelas Criadas

### 1. **Financials_backup (modo oculto - backup)**
   - Backup da tabela original para referência e segurança. Poderia ser eliminada para aumentar produtividade de processamento, caso necessário 
 
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
Feito conforme solicitado no exercicio mas na prática foi constatado que agrega pouco valor e não foi feito relacionamento com a tabela fato

### 4. **D_Descontos**
   - **Discount Band**:  Faixa de desconto.
   - **Discount Rate**: percentual de desconto vs sales price, conecta com a tabela fato (F_Vendas) e identifica qual Discount Band (banda de desconto - none, low, medium, high) 

### 5. **D_Manufacturing_Price**
   Foi identificado que o manufacturing price é constante para o produto, com isso, o parâmetro foi removido da tabela fato e foi criado uma nova tabela com a informação
    - **ID_produto**: Chave primária da tabela.
   - **Produto**: nome do produto
   - **Manufacturing_Price**: custo de manufatura, constante conforme o produto.

### 6. **D_Customer_ID**
   - **Customer_ID**: Chave primária da tabela de clientes, criada usando índice.
   - **Country**: Nome do país.
   - **Segment**: Segmento

### 7. **F_Vendas**: tabela fato
   - **SK_ID**: Chave substituta.
   - **ID_Produto**: Chave estrangeira para produtos.
   - **Produto**: Nome do produto.
   - **Customer_ID**: ID do cliente
   - **Units Sold**: Unidades vendidas.
   - **Sales Price**: Preço de venda.
   - *Gross Sales**: Vendas Brutas
   - **Discount**: Desconto em valor
   - **% Discount Rate**: percentual de desconto (vs sales price).
   - **Sales**: Vendas.
   - **COGS**: custo da mercadoria vendida.
   - **Profit**: Lucro
   - **Date**: Data da venda.

### 1. **D_Calendário**
   - Criada através da função DAX `CALENDAR()` para gerenciamento de datas. 

## Funções DAX Utilizadas

- **CALENDAR()**: Utilizada para criar a tabela `D_Calendário` e gerenciar datas no modelo.
- **Lucro**: (Vendas - COGS). Crida com intuito educativo para funções DAX, possui mesmo valor que o campo Profit (conforme print abaixo) da tabela fatos. Pode ser interessante utilizar esse campo e remover o campo "Profit" , usualmente não é verificado lucro para cada transação. 
- **Total acumulado de  Sales em Mês**: Vendas acumuladas somando-se mês a mês. 

## Processo de Construção do Diagrama

1. **Preparação dos Dados**: A tabela original *Financial Sample* foi copiada para criar a tabela *Financials_origem* para referência futura.
2. **Criação de Tabelas Dimensão e Fato**: A partir da tabela original, criamos tabelas de dimensão que armazenam informações como produtos, descontos e detalhes, enquanto a tabela fato concentra dados de vendas. Foram criados foreign keys e chaves primárias e excluidos dados não necessários
3. **Relacionamentos**: Definimos os relacionamentos entre as tabelas, conforme a metodologia do Star Schema, para garantir a eficiência das consultas.
4. **Organização das Colunas**: Colunas reorganizadas e renomeadas conforme o contexto e necessidade do modelo.
5. **Implementação de Funções DAX**: Funções DAX aplicadas para gerar colunas calculadas e métricas agregadas.


## Arquivo PBIX
O arquivo `.pbix` com a solução completa está disponível neste repositório.

## Conclusão

Este projeto implementa um modelo Star Schema eficaz para análise de dados financeiros. Utilizando Power BI e funções DAX, as informações foram organizadas em tabelas de dimensão e fato, proporcionando um modelo otimizado para consultas e relatórios.
