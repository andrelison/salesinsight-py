Mini-Projeto Avaliativo
SalesInsight PY - Analise e visualização de dado de vendas com python
Aluno: Andrlelison Felipe Martins

Sobre o projeto
O SalesInsight PY simula o trabalho de um analista de dados júnior de uma empresa de varejo. A partir de um histórico de vendas em CSV, o projeto carrega, limpa, transforma, agrega e visualiza os dados, gera insights para uma reunião de diretoria e exporta os resultados em CSV, JSON e PNG.
Todo o fluxo está organizado em funções reutilizáveis e na classe AnalisadorDeVendas.

O que o projeto analisa:
*Receita total, quantidade e número de vendas por mês
*Top 5 produtos e receita por categoria
*Desempenho por região (receita total e ticket médio)
*Segmentação de clientes por nível de gasto (Bronze, Prata e Ouro)
*Relação entre quantidade vendida e receita por transação
*Exportação de relatórios em CSV e JSON e de gráficos em PNG

Conceitos aplicados
*Lógica de programação: variáveis, tipos de dados, operadores aritméticos, lógicos e relacionais, if/elif/else e laços for
*Estruturas de dados: listas, dicionários (mapeamento de meses, relatório de limpeza, dicionário de métricas) e estruturas compostas
*Funções: parâmetros, retorno, docstrings, funções lambda e função de ordem superior (processar_coluna)
*Módulos e importação: pandas, numpy, json, re, os, random e datetime
*Leitura e escrita de arquivos: CSV (read_csv e to_csv) e JSON (json.dump e json.load)
*Módulo datetime: geração de datas e extração de mês, trimestre e ano
*Pandas: DataFrames, filtros booleanos, groupby com agg, apply e transformação condicional vetorizada com np.select
*Matplotlib e Seaborn: gráficos de linha, barras e dispersão, customização, subplots 2×2 e exportação em PNG
*Git e GitHub: branches descritivas, commits e Pull Requests

Resultados

Com o dataset sintético (seed=42), a execução produz:
*200 registros gerados, 6 com data inválida removidos, 194 registros analisados
*Receita total de R$ 1.380.210,31 e ticket médio de R$ 7.114,49
*Produto com maior receita: Notebook (R$ 493.242,63)
*Melhor mês: fevereiro (R$ 186.065,22). Pior mês: setembro (R$ 57.509,42)
*Maior receita por região: Centro-Oeste. Maior ticket médio: Nordeste
*Segmentação dos 49 clientes: 35 Ouro, 9 Prata e 5 Bronze

Decisões técnicas
Datas inválidas são removidas, não mantidas. Sem data não é possível calcular mês, trimestre nem a série temporal, e manter essas linhas distorceria as agregações por período. O relatório de limpeza informa quantos registros foram descartados.
Cada gráfico é uma função que desenha em um ax. Assim, a mesma função serve para a figura individual e para o painel 2×2, sem repetir código.
mes_nome vem de um dicionário em português, porque strftime("%B") retorna o mês em inglês no Colab.
seed=42 no gerador garante que qualquer pessoa reproduza exatamente os mesmos dados e resultados.

Possíveis melhorias
Ajustar as faixas de Bronze, Prata e Ouro: com os limites atuais, a maioria dos clientes cai em Ouro.
Agrupar por ano e mês, para funcionar com datas de mais de um ano (hoje todas são de 2025).
Incluir uma projeção simples de tendência de receita.

Ferramentas utilizadas
Python 3.10+
Google Colab / VS Code
Bibliotecas: pandas, numpy, matplotlib, seaborn, json, re, datetime, os, random
Git e GitHub (branches main, develop, feat/pipeline-dados e docs/readme)
