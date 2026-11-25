# SQL para análise de dados

Caderno de estudos criado para o desafio **Treinando uma IA de Aprendizagem**, da DIO. O objetivo é praticar consultas SQL que filtram registros, resumem resultados por grupo e cruzam tabelas, sempre conferindo a origem de cada explicação.

[Abrir o caderno no Gemini Notebook](https://notebook.google.com/notebook/1b3d0383-ad58-4bdc-be7d-109dc408657a). O link dá acesso de visualização. O Gemini Notebook pode solicitar login em uma conta Google.

## Fontes e curadoria

| Fonte | Formato | Por que foi incluída |
| --- | --- | --- |
| [Querying a Table — PostgreSQL 18](https://www.postgresql.org/docs/18/tutorial-select.html) | Documentação Web | Tutorial oficial com exemplos de seleção de colunas e filtros de linhas. |
| [Joins Between Tables — PostgreSQL 18](https://www.postgresql.org/docs/18/tutorial-join.html) | Documentação Web | Tutorial oficial que demonstra junções e mostra a origem dos `NULL` em um `LEFT JOIN`. |
| [Aggregate Functions — PostgreSQL 18](https://www.postgresql.org/docs/18/tutorial-agg.html) | Documentação Web | Tutorial oficial com exemplos de agregações, agrupamento e condições aplicadas antes e depois da agregação. |
| [CS50 SQL — Lecture 0: Querying](https://www.youtube.com/watch?v=vHYeChEf2lA) | Vídeo público com transcrição | Aula disponibilizada pelo curso aberto de Harvard, com exemplos introdutórios de consultas em SQLite. |
| [CS50 SQL — Lecture 1: Relating](https://cs50.harvard.edu/sql/notes/1/) | Notas da aula | Material didático oficial do mesmo curso, que explica as chaves, os tipos de junção e o agrupamento com exemplos. |

Usei o **Deep Research** para buscar fontes primárias sobre filtros, agrupamentos e junções. Entre as sugestões, importei somente as notas de *Relating* depois de conferir a publicação no site do curso. Os exemplos do CS50 usam SQLite e as outras fontes documentam PostgreSQL. As perguntas deste caderno exploram conceitos presentes nos dois sistemas.

## Diretriz usada no chat

> Atue como tutor de SQL para análise de dados, responda em português do Brasil e use somente as fontes selecionadas. Cite a fonte de cada afirmação técnica, use exemplos com dados fictícios quando ajudar e diga quando a base não sustentar uma resposta.

## Perguntas e respostas verificadas

| Pergunta feita ao notebook | Síntese da resposta | Fontes citadas no chat |
| --- | --- | --- |
| Qual a diferença entre `WHERE` e `HAVING` quando uso `GROUP BY` em uma análise de vendas? | `WHERE` filtra as linhas que entram na agregação, como as vendas de 2023. `HAVING` filtra os grupos resultantes, como clientes cujo `SUM(valor)` ficou acima de 5.000. | Citações 1 e 3 em [Aggregate Functions](https://www.postgresql.org/docs/18/tutorial-agg.html) e 2 em [Querying a Table](https://www.postgresql.org/docs/18/tutorial-select.html). |
| Por que um `LEFT JOIN` mantém clientes que não têm pedidos e o que aparece nas colunas de pedidos? | Com `clientes` à esquerda, a consulta mantém clientes sem correspondência. Para essas linhas, `id_pedido` e `valor` aparecem como `NULL`. | Citação 4 em [Joins Between Tables](https://www.postgresql.org/docs/18/tutorial-join.html) e 5 no [CS50 SQL — Querying](https://www.youtube.com/watch?v=vHYeChEf2lA), que explica `NULL`. |

Abri a citação 3 no próprio Gemini Notebook e conferi o parágrafo que explica em que momento cada filtro é aplicado. As perguntas foram respondidas com as quatro fontes iniciais. As notas de *Relating* entraram depois, na curadoria do Deep Research.

## Materiais e evidências

- [Mapa mental de SQL](mapa-mental.png)
- [Slides de revisão](slides-sql.pdf)
- [Captura do chat sobre WHERE e HAVING](chat-where-having.png)
- [Captura do chat sobre LEFT JOIN](chat-left-join.png)
