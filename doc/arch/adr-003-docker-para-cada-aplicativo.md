\# ADR 003: Docker para cada aplicativo



\## Contexto



O projeto é formado por três aplicativos (`facial-entry`, `facial-identify`

e `facial-manager`) e depende de serviços de apoio, como banco de dados,

cache e cofre de segredos. Ele deve rodar da mesma forma em Windows e

Linux, e cada aplicativo deve poder ser atualizado sem afetar os outros.



\## Decisão



Cada aplicativo é entregue como uma imagem Docker própria. Os serviços de

apoio também rodam em containers. No desenvolvimento, tudo sobe junto por

um arquivo `docker-compose.yml`. As imagens usam versões fixas, rodam com

um usuário sem privilégios e nunca contêm senhas ou chaves.



\## Status



Aceita.



\## Consequências



\- Cada aplicativo roda igual em qualquer máquina com Docker.

\- Cada aplicativo pode ser atualizado, reiniciado ou substituído sem

&#x20; afetar os outros.

\- O isolamento de um container é mais fraco que o de uma máquina virtual,

&#x20; porque todos compartilham o núcleo do sistema.

\- No Windows, os containers rodam pelo Docker Desktop com WSL 2.

\- Acessar a câmera de dentro de um container é trabalhoso no Windows,

&#x20; então o `facial-entry` também deve poder rodar fora do Docker.

\- As imagens com bibliotecas de visão computacional ficam grandes e

&#x20; precisam de varredura periódica de vulnerabilidades.

\- Os logs vão para a saída padrão, para não se perderem quando um

&#x20; container é recriado.

