# ADR 003: Docker para cada aplicativo



## Contexto



O projeto é formado por múltiplos aplicativos e cada um destes depende 
de um serviço auxiliar, como banco de dados, cache ou cofre de segredos. 
Ele precisa rodar tanto em Linux quanto em Windows. 
Cada aplicativo também deve poder ser atualizado sem afetar os outros.



## Decisão



Cada aplicativo é entregue como uma imagem Docker própria.
Os serviços auxiliares também estarão em suas respectivas imagens Docker. 
As imagens usam versões fixas, rodam com um usuário sem privilégios e 
nunca contém senhas ou chaves.



## Status



Aceita.



## Consequências



- Cada aplicativo roda igual em qualquer máquina com Docker.

- Cada aplicativo pode ser atualizado, reiniciado ou substituído sem

&#x20; afetar os outros.

- O isolamento de um container é mais fraco que o de uma máquina virtual,

&#x20; porque todos compartilham o núcleo do sistema.

- No Windows, os containers rodam pelo Docker Desktop com WSL 2.

\- Acessar a câmera de dentro de um container é trabalhoso no Windows,

&#x20; então o `facial-entry` também deve poder rodar fora do Docker.

\- As imagens com bibliotecas de visão computacional ficam grandes e

&#x20; precisam de varredura periódica de vulnerabilidades.
