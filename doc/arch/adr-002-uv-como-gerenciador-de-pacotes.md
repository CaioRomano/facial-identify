# ADR 002: uv como gerenciador de pacotes



## Contexto



As bibliotecas usadas no projeto precisam ter as versões fixadas, para
que as mesmas versões sejam instaladas em qualquer ambiente onde a
aplicação rode. A instalação dessas bibliotecas também precisa ser
simples e rápida.



## Decisão



O uv é o gerenciador de pacotes oficial do projeto. Ele cria os projetos,

instala as dependências e instala a versão do Python. Os arquivos

`pyproject.toml`, `uv.lock` e `.python-version` ficam no Git; a pasta

`.venv` não. As dependências de desenvolvimento ficam separadas das

dependências de execução.



## Status



Aceita.



## Consequências



- O `uv.lock` garante as mesmas versões das bibliotecas em todos os

&#x20; ambientes.

- Uma única ferramenta cuida das bibliotecas e da versão do Python.

- Quem trabalhar no projeto precisa instalar o uv e mantê-lo atualizado,

&#x20; as versões do Python que ele consegue baixar dependem da versão do próprio uv.

- O uv é mais rápido na instalação dos pacotes e substitui diversas ferramentas, como o pip e Poetry e o venv, permitindo maior simplicidade de configuração.
