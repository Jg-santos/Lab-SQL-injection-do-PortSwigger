# Lab-SQL-injection-do-PortSwigger
Passo a Passo do primeiro lab do PortSwigger SQL injection vulnerability in WHERE clause allowing retrieval of hidden data
esse lab pode ser encontrado na pagina do Portswigger:

https://portswigger.net/web-security/sql-injection/lab-retrieve-hidden-data


A descrição do Lab é a seguinte:

This lab contains a SQL injection vulnerability in the product category filter. When the user selects a category, the application carries out a SQL query like the following:
SELECT * FROM products WHERE category = 'Gifts' AND released = 1
To solve the lab, perform a SQL injection attack that causes the application to display one or more unreleased products.

Este laboratório contém uma vulnerabilidade de injeção de SQL no filtro de categoria de produtos. Quando o usuário seleciona uma categoria, o aplicativo executa uma consulta SQL como a seguinte: SELECT * FROM products WHERE category = 'Gifts' AND released = 1. 
Para resolver o laboratório, execute um ataque de injeção de SQL que faça com que o aplicativo exiba um ou mais produtos não lançados.

É um lab bem simples e sem nenhuma proteção contra ataques sql, portanto com o direcionamento que foi dado na descrição do lab, sabemos que devemos atacar na aba gifts

https://0adf001f0474b89183b9b46700380087.web-security-academy.net/filter?category=Gifts

ao entrar na aba gifts precisamos fazer uma consulta que traga um produto não listado.
o jeito mais comum de fazer isso é usando um payload sql para dar bypass
no próprio portswigger tem uma página com vários payloads para serem usados
https://portswigger.net/web-security/sql-injection/cheat-sheet
o mais comum de ser usado para prova de conceito de se uma aplicação é vulnerável a sql é o:

'or+1=1--

onde:
•	' - fecha uma string em uma consulta SQL
•	or - Operador SQL
•	1=1 - Condição sempre verdadeira
•	-- - Comentário SQL (ignora o restante da consulta)

Assim que a prova de conceito é lançada a vulnerabilidade fica visível na tela e o lab se torna concluído.

https://0adf001f0474b89183b9b46700380087.web-security-academy.net/filter?category=Gifts'or+1=1--



