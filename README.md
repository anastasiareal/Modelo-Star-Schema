# Projeto: Modelo Star Schema — Financial Sample

Este repositório contém o projeto Power BI que transforma a tabela única Financial Sample em um modelo analítico no formato star schema. O objetivo é transformar dados transacionais em uma estrutura otimizada para análise: uma tabela fato central (F_Vendas) e várias tabelas dimensão (D_Produtos, D_Produtos_Detalhes, D_Descontos, D_Detalhes, D_Calendário).




🔧 1. **Preparação e Organização dos Dados**

Tudo começa com a importação da tabela _Financial Sample_, que contém todas as informações originais. A partir dela foi feita uma cópia  e foi criada com o nome _Financials_Origem_, mantida em modo oculto para servir como backup e referência.

Essa estrutura inicial foi utilizada como base para o desmembramento das outras tabelas.



🧱 2. **Criação das Tabelas Dimensão e Fato**

Com o objetivo de implementar um Star Schema, a tabela principal foi reorganizada e dividida em:

Dimensões criadas:

🔹 **_D_Produtos_**

Contém informações agregadas sobre produtos.

ID_Produto

Produto

Média de Unidades Vendidas

Média do Valor de Vendas

Mediana do Valor de Vendas

Valor Máximo de Venda

Valor Mínimo de Venda

🔹 **_D_Produtos_Detalhes_**

Reúne detalhes complementares dos produtos.

ID_produtos

Discount Band

Sale Price

Units Sold

Manufacturing Price

🔹 **_D_Descontos_**

Dimensão exclusiva para análises de descontos.

ID_Produto

Discount

Discount Band

🔹 **_D_Detalhes_**

Dimensão utilizada para atributos como Segment, Country, etc.

(Campos definidos a partir das necessidades analíticas)

🔹 **_D_Calendário_**

Criada diretamente no Power Query, sem DAX. Inclui:

Ano

Mês

Dia

Trimestre

Nome do Mês

Número da Semana

Indicador de final de semana

🔹 **_F_Vendas_**

Tabela fato principal, armazenando o nível mais granular do evento de venda.

SK_ID

ID_Produto

Produto

Units Sold

Sales Price

Discount Band

Segment

Country

Sales

Profit

Date









📅 3. **Construção da Tabela Calendário**

- A tabela de calendário foi criada no Power Query, garantindo independência da tabela fato e possibilitando cálculos temporais avançados.

- O script incluído gera datas, nomes, indicadores semanais e estrutura fiscal.




🧽 4. **Transformações Aplicadas no Power Query**

- Verificação e correção de tipos de dados

- Padronização de valores monetários

- Checagem e tratamento de valores nulos

- Criação de colunas derivadas

- Organização das tabelas em grupos (Fato / Dimensões)






📈 5. **Benefícios da Modelagem Dimensional**

- Melhor desempenho em análises

- Relacionamentos claros e bem definidos

- Facilidade para criar medidas e KPIs

- Estrutura ideal para painéis corporativos
