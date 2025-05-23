
# 📊 Projeto Power BI - Marketing

## 1. Informações Gerais do Projeto

**Nome do Projeto:** Análise de dados de Marketing  
**Responsável:** Renan Costa  
**Data de Início:** 25/03/2025  
**Data de Conclusão:** 27/03/2025  
**Versão Atual:** 1.0  
**Setor/Departamento:** Marketing  

---

## 2. Objetivo do Projeto

**Resumo:** Este projeto tem como objetivo apresentar métricas gerais sobre a percepção do cliente, seu comportamento de compra, a performance das campanhas de marketing desenvolvidas e os padrões de consumo por ponto de venda (país).

---

## 3. Fontes de Dados

**Origem dos Dados:** Dados fictícios em arquivos CSV fornecidos pela Data Science Academy.

**Tabela e Campos Utilizados:**

**DadosMarketing:**  
- Informações Pessoais  
  - Ano Nascimento  
  - Escolaridade  
  - Estado Civil  
  - Salario Anual  
  - Filhos em Casa  
  - Adolescentes em Casa  

- Gastos por Categoria  
  - Gasto com Eletronicos  
  - Gasto com Brinquedos  
  - Gasto com Moveis  
  - Gasto com Utilidades  
  - Gasto com Alimentos  
  - Gasto com Vestuario  

- Comportamento de Compra  
  - Numero de Compras com Desconto  
  - Numero de Compras na Web  
  - Numero de Compras via Catalago  
  - Numero de Compras na Loja  
  - Numero Visitas WebSite Mes  

- Engajamento em Campanhas  
  - Compra na Campanha 1  
  - Compra na Campanha 2  
  - Compra na Campanha 3  
  - Compra na Campanha 4  
  - Compra na Campanha 5  

- Outros Dados  
  - Comprou  
  - Pais  

---

## 4. Tratamento de Dados

**Transformações Realizadas no Power Query:**  
- **Remoção de Outlier**: Foi identificado um cliente com um **Salário Anual de 666.666**, um valor atípico e fora do padrão esperado. Para garantir a qualidade da análise, esse registro foi removido.  
- **Alteração de Tipos de Dados**: A coluna **Comprou** teve seu tipo alterado de **Número Inteiro** para **Texto**. Embora os valores dessa coluna sejam 0 e 1, a modificação foi necessária para que ela fosse tratada como uma categoria nos visuais.  
- **Alteração de Valores dos Dados**: Para melhorar a compreensão dos gráficos, os valores da coluna **Comprou** foram ajustados: **0** foi substituído por **"Não"** e **1** por **"Sim"**.

---

## 5. Validação e Verificação dos Dados

**Métodos de Validação:** Verificação Manual.  
**Erros Encontrados e Correções:** Nenhum erro encontrado.

---

## 6. Modelagem de Dados

**Relacionamentos Criados:** Tabela única.

---

## 7. Funções DAX Utilizadas

### Medidas Criadas (DAX):
- **Média de Salário Anual:**
  ``` DAX
  AVERAGE(DadosMarketing[Salario Anual])
  ```
- **Total de Clientes:** 
  ``` DAX
  COUNT(DadosMarketing[ID])
  ```  
- **Total de Compras:**  
  ``` DAX
  SUM(DadosMarketing[Total de Compras])
  ```  
- **Total de Compras com Desconto:**
  ``` DAX
  SUM(DadosMarketing[Numero de Compras com Desconto])
  ```  
- **Total de Compras na Loja:** 
  ``` DAX
  SUM(DadosMarketing[Numero de Compras na Loja])
  ```  
- **Total de Compras na Web:** 
  ``` DAX
  SUM(DadosMarketing[Numero de Compras na Web])
  ```  
- **Total de Compras via Catálogo:**
  ``` DAX
  SUM(DadosMarketing[Numero de Compras na Loja])
  ```  
- **Total de Gastos:**
  ``` DAX
  SUM(DadosMarketing[Total de Gastos])
  ```  
- **Total de Visitas ao WebSite no Mês:**
  ``` DAX
  SUM(DadosMarketing[Numero Visitas WebSite Mes])
  ```  

### Colunas Calculadas (DAX):
- **Total de Compras:** 
  ``` DAX
  DadosMarketing[Numero de Compras com Desconto] 
  + DadosMarketing[Numero de Compras na Loja] 
  + DadosMarketing[Numero de Compras na Web] 
  + DadosMarketing[Numero de Compras via Catalogo]
  ```
- **Total de Gastos:**
  ``` DAX
  DadosMarketing[Gasto com Alimentos] 
  + DadosMarketing[Gasto com Brinquedos] 
  + DadosMarketing[Gasto com Eletronicos] 
  + DadosMarketing[Gasto com Moveis] 
  + DadosMarketing[Gasto com Utilidades] 
  + DadosMarketing[Gasto com Vestuario]
  ```

---

## 8. Dashboards e Relatórios

### Visão do Cliente:

![image](https://github.com/user-attachments/assets/152aef24-4adb-4b8f-8b6a-0fddf68dcee0)

#### 1. Perfil Geral dos Clientes  
- O total de clientes é **1.999**, um número relevante para análise do comportamento de consumo.  
- A **média salarial** dos clientes é de **R$ 51.981**, indicando um público de poder aquisitivo médio a alto.

#### 2. Padrões de Compra  
- A maioria das compras acontece **nas lojas físicas (11.592)**, seguida das **compras na web (8.147)** e **via catálogo (5.270)**.  
- **4.661 compras foram feitas com desconto**, mostrando que uma parcela considerável dos clientes é sensível a promoções.

#### 3. Segmentação por País  
- Os **Estados Unidos lideram em volume de compras (14,3 mil)**, sugerindo um mercado prioritário.  
- **Espanha e Chile** também têm um número expressivo de compras **(4,6 mil e 3,7 mil, respectivamente)**, representando oportunidades de crescimento.  
- **Brasil, Argentina, Portugal e Alemanha** apresentam números menores, mas ainda significativos. Estratégias específicas podem ser necessárias para aumentar as vendas nesses países.

#### 4. Estado Civil dos Clientes  
- A maioria dos clientes é **solteira (59,88%)**, seguida por **casados (26,11%)** e **divorciados (14,01%)**.  
- Como a maior parte do público é solteira, estratégias de marketing podem focar em benefícios individuais, como programas de fidelidade personalizados, produtos para o público jovem ou experiências exclusivas para solteiros.

#### 5. Escolaridade dos Clientes  
- O maior grupo tem **curso superior (999 clientes)**, seguido por **doutorado (437)**, **mestrado (337)**, **segundo grau (177)** e **primeiro grau (49)**.  
- Isso sugere que o público tem um alto nível de instrução, o que pode impactar na escolha de produtos e na forma de abordagem de marketing.

### Visão Comportamental dos Gastos:

![image](https://github.com/user-attachments/assets/796c6e7e-a3de-45a7-95fa-1b503fa63e1e)

#### 1. Gastos por Salário Anual  
- O total de gastos dos clientes cresce proporcionalmente ao **salário anual**.  
- A maioria dos clientes seguem esse padrão, mas há exceções: alguns clientes com **salário acima de R$ 150.000 gastam menos que outros com salários inferiores**.  
- Isso pode indicar um perfil mais conservador financeiramente ou um estilo de vida mais econômico.

#### 2. Gastos por Quantidade de Filhos em Casa  
- Clientes **sem filhos em casa** são os que apresentam **maior total de gastos**.  
- Esse comportamento pode estar ligado ao fato de que a maioria dos clientes é **solteira**, possuindo mais renda disponível para consumo.

#### 3. Estado Civil e Gastos  
- A maior parte dos gastos vem de clientes **solteiros (R$ 707.515)**, seguidos por **casados (R$ 319.107)** e **divorciados (R$ 178.187)**.  
- Esse padrão indica que solteiros podem ter mais flexibilidade financeira para gastos discricionários.

#### 4. Escolaridade e Gastos  
- O maior volume de gastos está associado a clientes com **curso superior (R$ 364.307)**, seguidos por **doutorado (R$ 170.160)** e **mestrado (R$ 119.945)**.  
- Clientes com **segundo grau (R$ 50.960)** e **primeiro grau (R$ 2.143)** gastam significativamente menos.  
- Esse comportamento sugere que **quanto maior o nível de escolaridade, maior a propensão a gastar**, possivelmente devido a melhores oportunidades de renda.

### Visão da Performance das Campanhas:

![image](https://github.com/user-attachments/assets/c688ff81-83e7-4d2f-b468-ee019efbc5eb)

#### 1. Performance Geral  
- **A maioria dos clientes (83,99%) não comprou**, enquanto apenas **16,01% efetuaram a compra**.  
- Clientes que **compraram têm uma média salarial de R$ 59.000**, enquanto os que **não compraram têm uma média salarial de R$ 51.000**. Ou seja, pessoas com média salarial maior compraram mais.

#### 2. Acessos ao WebSite  
- Clientes que realizaram alguma compra visitaram o WebSite **1703 vezes**, já os que não realizaram visitaram **8946 vezes**.  
- **Pessoas com Curso Superior e Doutorado visitam mais o site**, independentemente de realizarem uma compra ou não.

#### 3. Relação Entre as Campanhas e a Quantidade de Filhos em Casa  
- Clientes sem filhos são maioria tanto entre os que **não compraram (936)** quanto entre os que **compraram (208)**.  
- Clientes com **1 filho também apresentam um número razoável de compras (110)**, mas ainda assim a maioria não compra (706).  
- Poucos clientes com **2 filhos ou mais compraram (apenas 2), o que pode indicar que esse grupo não se interessa tanto pelo produto**.

### Visão Pontos de Venda:

![image](https://github.com/user-attachments/assets/14f01e56-8267-40fb-b08a-9307e848dac4)

#### 1. Gastos em Diferentes Categorias  
- A maior parte dos gastos é com produtos **eletrônicos**, seguida por **móveis**. Esse padrão se mantém em todos os países.

#### 2. Gastos por Ano  
- O total de gastos de cada país **permanece constante** nos anos de **2018** e **2019**. Em **2020**, há um **grande crescimento** – possivelmente devido ao início da pandemia. Logo após, em **2021**, ocorre uma **queda considerável**, seguida de um **crescimento contínuo** até **2023**.  
- **Padrão Global:** Todos os países seguem essa tendência.  
- **Destaque:** Os **Estados Unidos** apresentam o **maior valor bruto** de gastos.

---

## 9. Acesso e Compartilhamento

**Modo de Compartilhamento:** Publicado no Power BI Service  
[🔗 Acessar Dashboard](https://app.powerbi.com/view?r=eyJrIjoiYjU5NmE5MGYtZWQ3Zi00NDkzLWE5YTEtODU1MDZlOWY5NTdjIiwidCI6ImJhZTkwYjYxLTg4OTItNDQyMC1hMTEyLTE0NTQ4MzBkYmJiOSJ9&pageName=134ed5756e9c2c0d7574)

---

## 10. Considerações Finais

Esse projeto foi desenvolvido a partir do curso **“Microsoft Power BI Para Business Intelligence e Data Science”** da **Data Science Academy**.  
A fonte de dados foi fornecida pelo curso.

Nesse projeto eu aprendi bastante sobre análise de dados, não apenas apresentar esses dados em gráficos.  
A maioria dos gráficos foram criados com base na análise e explicação do curso da Data Science Academy.  
O contrário da organização dos dashboards, da tela de fundo e coloração, que foram desenvolvidas inteiramente por mim.

> ⚠️ **Nota:** Os gráficos do dashboard **Visão Pontos de Venda** apresentam muita informação agrupada em um único gráfico, dificultando a análise e entendimento dos mesmos. Ajustar essa visualização é um aspecto de melhoria futura.
