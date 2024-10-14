# Projeto: Integração de Base de Dados SQL no Azure com Power BI

Este projeto consiste na criação e implementação de uma base de dados no **Azure SQL** e sua integração com o **Power BI** para análise e visualização dos dados. O principal foco do projeto foi a **limpeza e transformação dos dados**, garantindo que a base fosse adequada para gerar relatórios e insights precisos.

## Objetivo

O objetivo deste projeto foi conectar uma base de dados hospedada no **Azure SQL** ao **Power BI**, aplicar técnicas de limpeza e transformação, e construir relatórios confiáveis que pudessem auxiliar na tomada de decisões. A transformação dos dados envolveu diversas etapas para assegurar que os dados fossem consistentes e precisos antes da análise final.
Abaixo um print da base hospedada no Azure.

![Azure](./Images/Azure%20part1.PNG)

![Databases e Tabelas](./Images/Azure%20part2%20Databases%20%26%20Tables.PNG)

![Conteudo Tabela](./Images/Azure%20part3%20conteudo%20tabela.PNG)

## Principais Etapas de Limpeza e Transformação

### 1. Limpeza da Base de Dados
- **Remoção de registros duplicados** e dados inconsistentes.
- **Validação de integridade** dos dados em todas as tabelas, eliminando valores inválidos ou fora do padrão.

### 2. Eliminação de Colunas Desnecessárias
- Identificação de colunas que não agregavam valor para as análises.
- Remoção de colunas redundantes ou que continham informações irrelevantes para o projeto.

### 3. Junção de Colunas
- Criação de novas colunas combinando informações relevantes, como:
  - **Colunas de nome completo** a partir de colunas de primeiro e último nome.
  - **Colunas de endereço completo**, combinando rua, número e complemento.

### 4. Divisão de Colunas Completas (Ex: Data Completa)
- Separação de colunas que continham múltiplas informações, como datas completas, em:
  - **Ano**, **Mês** e **Dia** para facilitar a análise temporal.
  - Criação de colunas de data apropriadas para análises detalhadas e agrupamentos por períodos específicos.

### 5. Junção de Tabelas
- **Criação de relacionamentos** entre diferentes tabelas do banco de dados para gerar uma visão mais integrada.
- **Mescla de tabelas** relacionadas através de chaves primárias e estrangeiras para criar uma tabela mais abrangente para análise.

### 6. Tratamento de Dados
- **Campos faltantes**: Substituição ou exclusão de valores nulos ou ausentes utilizando:
- **Modificação de tipos de dados**: Ajuste dos tipos de dados para garantir compatibilidade e otimizar as análises no Power BI (ex: conversão de strings para datas ou números).
- **Agrupamento de dados**: Criação de grupos juntando 2 colunas
- **Mescla de consultas**: Consolidação de diferentes consultas em uma única tabela, evitando duplicidade de dados e permitindo uma análise mais integrada e eficiente.

## Conexão entre Azure SQL e Power BI

A integração foi feita diretamente no **Power BI**, conectando-se ao banco de dados do **Azure SQL** via consulta SQL. Isso permitiu trazer os dados necessários para o ambiente de Power BI e aplicar todas as transformações diretamente na interface da ferramenta.

## Conclusão

Após a limpeza e transformação dos dados, a base pode ser utilizada para gerar relatórios e dashboards no Power BI, que proporcionaram insights valiosos. 

![Relatório](./Power%20BI%20Relatorio.PNG)

## Ferramentas Utilizadas

- **Azure SQL**: Para armazenamento e gerenciamento da base de dados.
- **Power BI**: Para limpeza, transformação e visualização dos dados.
- **SQL**: Para consultas e integração entre o banco de dados e o Power BI.

## Próximos Passos

- Exploração de dados adicionais para identificar novas oportunidades de análise.
- Automatização dos relatórios para atualização em tempo real.
