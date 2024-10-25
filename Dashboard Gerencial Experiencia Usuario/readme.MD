# Projeto Power BI - Análise de Vendas e Lucratividade

Este projeto de **Power BI** tem como objetivo a criação de um **dashboard interativo** focado na análise de **Vendas, Lucro** e **Detalhes de Vendas**, com a inclusão de elementos visuais e funcionalidades que melhoram a navegação e a interpretação dos dados.

## Alterações e Funcionalidades Implementadas

### 1. Utilização da Proporção Áurea
- O layout do relatório foi estruturado utilizando a **proporção áurea**, com foco em uma disposição visual harmônica, permitindo ao usuário uma melhor fluidez e entendimento das informações.

### 2. Botão de Navegabilidade
- Implementação de botões de **navegabilidade** entre as páginas, com uso de **contraste de cores** e design focado em **focalização** e **seleção**, facilitando a interação do usuário com o relatório.
Abaixo um exemplo com focalização na seleção do gráfico de vendas por segmento (em contraste roxo)

![Foco Segmentacao](./Images/Pagina%201%20-%20focalizacao.PNG)

### 3. Definição de Gráficos e Métricas Relevantes
- Para cada página do relatório (Vendas, Lucro e Detalhe de Vendas), foram definidos os **gráficos e métricas mais relevantes**, garantindo foco em informações críticas para o negócio.

### 4. Inclusão de Métricas de Negócio
- Métricas importantes para a análise, como **margem de lucro** (Lucro / Vendas), foram incluídas, possibilitando insights aprofundados sobre a rentabilidade da operação.

### 5. Cores
- Definido cores neutras e suaves, que não distraiam o usuário e permitam que os dados se destaquem. Além disso, buscou-se manter o padrão de cores ao longo dos relatórios, como no caso de "países", onde utilizei a mesma cor para cada país em todos os gráficos, tanto na página de vendas como lucro (ex: Bordô: #800020 para Estados Unidos)

### 6. Métricas anuais
- Em relatórios corporativos, os indicadores raramente são apresentados de forma acumulada por mais de um ano. Por isso, foi aplicado um filtro para exibir os dados de forma anualizada.                                                                                                                                                                                                                                                                                       
                                                                                                                                                                                                                                                                                                        
## Estrutura das Páginas

### Página de **Vendas**
- **Métricas principais**:
  - Vendas mensais (sazonalidade)
  - Vendas por país e segmento (métrica mais relevante, pode-se mensurar capilaridade)
- Foco em identificar padrões de sazonalidade e variações de vendas por regiões e segmentos.

![Pagina 1](./Images/Pagina%201%20-%20Vendas.PNG)

### Página de **Lucro**
- **Métricas principais**:
  - Lucratividade trimestral (relatórios financeiros são geralmente mais relevantes em fechamento de trimestre) 
  - Abertura por produto (mais relevante que segmento para essa métrica) e país 
  - Comparação de **margem (preço vs custo)** por produto
- Análise voltada para relatórios financeiros, com ênfase em lucratividade por produto e país ao longo dos trimestres.

![Pagina 2](./Images/Pagina%202%20-%20Lucro.PNG)

### Página de **Detalhe de Vendas**
- **Segmentação por produto**:
  - Subsegmentada em **país, segmento (canal), trimestre e percentual net sales gross sales**.
- Foco na análise detalhada de vendas para fornecer insights aprofundados sobre desempenho por categorias.

![Pagina 3](./Images/Pagina%203%20-%20Detalhe%20de%20Vendas.PNG)

