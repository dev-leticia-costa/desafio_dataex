Aqui está uma estrutura de README elaborada especificamente para destacar suas habilidades em Engenharia de Dados, modelagem e boas práticas, chamando a atenção de tech leads e recrutadores.

🏗️ Construção de Data Warehouse: Despesas Públicas
Este projeto demonstra a construção ponta a ponta de um Data Warehouse utilizando SQL Server (T-SQL), aplicando o conceito de Arquitetura Medalhão (Bronze, Silver e Gold) e a modelagem dimensional Star Schema.

O objetivo do projeto é ingerir dados brutos de despesas públicas oriundos de arquivos CSV, transformá-los e disponibilizá-los em uma estrutura otimizada para consultas analíticas e geração de insights (Business Intelligence).

🚀 Tecnologias e Habilidades Demonstradas
Linguagem: SQL Server / T-SQL

Engenharia de Dados: Processos de ETL/ELT, Bulk Insert, Merge (Upsert)

Arquitetura de Dados: Arquitetura Medalhão (Bronze, Silver, Gold)

Modelagem de Dados: Star Schema (Tabelas Fato e Dimensão)

Governança e Auditoria: Criação de rotinas de Log e tratamento de erros (Try/Catch)

Análise de Dados: Agregações complexas, CTEs, e cálculos de variação MoM (Month-over-Month)

🏛️ Arquitetura do Projeto
O pipeline de dados foi desenhado para garantir a qualidade, rastreabilidade e performance dos dados, dividido nas seguintes camadas:

Camada Bronze (Raw Data): Ingestão dos dados brutos diretamente de arquivos CSV (BULK INSERT) para tabelas sem tratamento rigoroso, garantindo a preservação do dado original.

Camada Silver (Cleansed Data): Refinamento dos dados e criação das Tabelas Dimensão (D_Orgao_Superior, D_Orgao_Subordinado, D_Unidade_Gestora, D_Gestao, D_Grupo_Despesa e D_Tempo).

Camada Gold (Curated Data): Construção da Tabela Fato (FATO_DESPESA). O carregamento desta camada utiliza a instrução MERGE para realizar Upserts seguros, garantindo que registros existentes sejam atualizados e novos sejam inseridos sem duplicidade.

Camada de Log (Auditoria): Implementação de uma tabela LOG_CARGAS que registra o histórico das execuções, gravando o sucesso ou os detalhes do erro (número, severidade, linha) através de blocos BEGIN TRY... CATCH e controle transacional (BEGIN TRANSACTION / COMMIT / ROLLBACK).

📊 Insights e Consultas Analíticas (Business Questions)
Com a camada Gold estabelecida, o projeto responde a perguntas cruciais de negócios, demonstrando fluência em manipulação de dados para BI:

Quais são os Top 10 Órgãos Superiores com maior valor pago em um mês específico?

Qual é o valor total empenhado consolidado por Gestão no trimestre?

Qual é a Variação Percentual (MoM) do valor empenhado de um mês para o outro por Unidade Gestora?

💡 Destaques do Código
Performance: Uso de OPTIMIZE_FOR_SEQUENTIAL_KEY = OFF e chaves primárias bem definidas (Primary Key Clustered) para garantir a eficiência das junções.

Tratamento de Dados: Conversão segura de tipos de dados durante a análise, como a substituição de vírgulas e casting para decimal(18,4) (CAST(REPLACE(valor, ',', '.') AS decimal...)).

⚙️ Como Executar
Clone o repositório.

Certifique-se de ter um ambiente SQL Server configurado.

Altere os caminhos dos arquivos CSV nos comandos BULK INSERT para refletir o diretório local da sua máquina.

Execute os blocos do notebook sequencialmente.

Autor(a): Letícia Costa

LinkedIn: https://www.linkedin.com/in/let%C3%ADcia-c-b81187237/

Portfólio: github.com/dev-leticia-costa
