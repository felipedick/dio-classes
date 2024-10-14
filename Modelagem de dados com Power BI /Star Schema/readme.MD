# Projeto: Construção de Star Schema para Análise de Professores

Este projeto envolve a modelagem de um **Star Schema** para facilitar a análise de dados relacionados aos professores em uma instituição de ensino. O objetivo é organizar as informações de forma otimizada para consultas e relatórios, utilizando uma abordagem dimensional.
Além disso, a partir do diagrama original, foram eliminadas tabelas sem necessidade, como por exemplo, informações de "aluno".

## Estrutura do Star Schema

O modelo segue a arquitetura de um **Star Schema**, onde a tabela central (fato) é conectada às tabelas dimensionais. Abaixo estão os principais componentes:

### Tabela Fato: `FATO PROFESSOR`
A tabela fato armazena os eventos ou transações principais, representando a alocação de professores em disciplinas, cursos e departamentos ao longo do tempo.

- **Colunas**:
  - `ID PROFESSOR` (chave estrangeira para `DIM PROFESSOR`)
  - `ID DISCIPLINA` (chave estrangeira para `DIM DISCIPLINA`)
  - `ID DEPARTAMENTO` (chave estrangeira para `DIM DEPARTAMENTO`)
  - `ID CURSO` (chave estrangeira para `DIM CURSO`)
  - `DATA` (chave estrangeira para `DIM DATA`)
  - `QUANTIDADE HORAS` (métrica, número de horas alocadas ao professor)

### Tabelas Dimensionais

As tabelas dimensionais fornecem detalhes descritivos sobre as entidades relacionadas à tabela fato. As principais dimensões são:

#### 1. `DIM PROFESSOR`
- **Descrição**: Armazena informações sobre os professores.
- **Colunas**:
  - `ID PROFESSOR` (chave primária)
  - `NOME DO PROFESSOR`

#### 2. `DIM DISCIPLINA`
- **Descrição**: Detalha as disciplinas que os professores lecionam.
- **Colunas**:
  - `ID DISCIPLINA` (chave primária)
  - `NOME DA DISCIPLINA`

#### 3. `DIM DEPARTAMENTO`
- **Descrição**: Contém informações sobre os departamentos da instituição.
- **Colunas**:
  - `ID DEPARTAMENTO` (chave primária)
  - `NOME DO DEPARTAMENTO`
  - `CAMPUS`
  - `NOME DO PROFESSOR COORDENADOR`

#### 4. `DIM CURSO`
- **Descrição**: Informa sobre os cursos disponíveis.
- **Colunas**:
  - `ID CURSO` (chave primária)
  - `NOME DO CURSO`

#### 5. `DIM DATA`
- **Descrição**: Detalha informações temporais que permitem análises ao longo do tempo.
- **Colunas**:
  - `DATA` (chave primária)
  - `ANO`
  - `SEMESTRE`
  - `MÊS`
  - `DIA DA SEMANA`

## Uso do Star Schema

O **Star Schema** foi projetado para consultas rápidas e eficientes, ideal para relatórios de BI. Ele permite a análise de métricas como a quantidade de horas dos professores por curso, departamento, disciplina e ao longo do tempo (mês, semestre, etc.).

### Exemplo de Análises:
- Horas lecionadas por professor em um determinado curso e semestre.
- Distribuição das horas de aula por departamento e campus.
- Comparação da carga horária entre disciplinas ao longo do tempo.

## Considerações

A abordagem de Star Schema simplifica a consulta dos dados, oferecendo um modelo otimizado para relatórios analíticos em ferramentas de BI. As dimensões detalhadas permitem múltiplos cortes e visualizações das informações.
