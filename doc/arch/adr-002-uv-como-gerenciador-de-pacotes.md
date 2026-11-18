\# ADR 002: uv como gerenciador de pacotes



\## Contexto



O projeto em Python precisa instalar as mesmas versões das bibliotecas em

qualquer computador, no CI e dentro das imagens Docker. Também precisa

instalar e fixar a versão do próprio Python. As alternativas consideradas

foram o pip com venv e o Poetry.



\## Decisão



O uv é o gerenciador de pacotes oficial do projeto. Ele cria os projetos,

instala as dependências e instala a versão do Python. Os arquivos

`pyproject.toml`, `uv.lock` e `.python-version` ficam no Git; a pasta

`.venv` não. As dependências de desenvolvimento ficam separadas das

dependências de execução.



\## Status



Aceita.



\## Consequências



\- O `uv.lock` garante as mesmas versões das bibliotecas em todos os

&#x20; ambientes.

\- Uma única ferramenta cuida das bibliotecas e da versão do Python.

\- Quem trabalhar no projeto precisa instalar o uv e mantê-lo atualizado,

&#x20; porque a lista de versões do Python que ele oferece depende da versão

&#x20; do próprio uv.

\- O uv é mais recente que o pip e o Poetry, então há menos material de

&#x20; apoio sobre ele.

