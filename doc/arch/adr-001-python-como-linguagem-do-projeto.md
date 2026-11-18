\# ADR 001: Python 3.13 como linguagem oficial do projeto



\## Contexto



O projeto precisa de uma linguagem principal para todos os seus serviços.

O desenvolvedor tem mais conhecimento em Python do que em outras linguagens

e já conhece boa parte das ferramentas previstas para o projeto. As

bibliotecas de visão computacional que o projeto vai usar, como o OpenCV,

têm suporte direto em Python e oferecem pacotes oficiais para a série 3.13.



\## Decisão



O Python é a linguagem oficial do projeto, na série 3.13, a partir da

versão 3.13.18. A versão exata fica fixada no arquivo `.python-version`

do repositório e é atualizada a cada nova correção de segurança da série.



\## Status



Aceita.



\## Consequências



\- O desenvolvimento avança mais rápido, porque usa a linguagem que o

&#x20; desenvolvedor domina.

\- O Python é mais lento que linguagens compiladas, mas o processamento

&#x20; pesado roda em código nativo dentro das bibliotecas.

\- Para atender mais pedidos ao mesmo tempo, o projeto escala com mais

&#x20; processos ou instâncias, por causa do GIL.

\- A série 3.13 recebe apenas correções de segurança até outubro de 2028;

&#x20; antes disso, o projeto precisa migrar para uma série mais nova.

\- Subir de série exige confirmar antes que as bibliotecas do projeto têm

&#x20; pacotes oficiais para ela.

\- A variante sem GIL (free-threaded) não é usada.

