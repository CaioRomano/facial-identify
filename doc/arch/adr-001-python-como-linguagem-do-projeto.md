# ADR 001: Python como linguagem oficial do projeto



## Contexto



O projeto precisa de uma linguagem de programação que possa unir os componentes de reconhecimento, 
gerenciamento do banco de dados e os demais componentes do projeto sob uma única linguagem. 
O desenvolvedor, por sua vez, precisa trabalhar numa linguagem na qual esteja mais familiarizado, no intuito de 
agilizar o desenvolvimento da aplicação. Além disso, principalmente na parte de reconhecimento facial e detecção de rosto, suas respectivas bibliotecas devem possuir suporte para a linguagem usada no projeto.



## Decisão



O Python é a linguagem oficial do projeto, da versão 3.13.18, por possuir suporte para os modelos de detecção de rosto e 
reconhecimento facial a serem usados nesta versão da aplicação.



## Status



Aceita.



## Consequências



- O desenvolvimento avança mais rápido, porque usa a linguagem que o

&#x20; desenvolvedor domina.

- O Python é mais lento que linguagens compiladas, mas o processamento

&#x20; pesado roda em código nativo dentro das bibliotecas.

- Subir de série exige confirmar antes que as bibliotecas do projeto têm

&#x20; pacotes oficiais para ela.

- A versão 3.14 não será usada.

- versões futuras das bibliotecas podem deixar de suportar o Python 3.13.
