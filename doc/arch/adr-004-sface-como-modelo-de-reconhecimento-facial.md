\# ADR 004: SFace como modelo de reconhecimento facial







\## Contexto







O projeto precisa transformar cada rosto em um embedding, para comparar

uma pessoa com as pessoas cadastradas. O modelo precisa rodar em CPU, ter

licença que permita uso comercial e funcionar pelo OpenCV. Foram

considerados o SFace (OpenCV Zoo), o modelo de reconhecimento do dlib e os

modelos pré-treinados do InsightFace.







\## Decisão







O SFace, distribuído pelo OpenCV Zoo em formato ONNX, é o modelo de

reconhecimento facial do projeto. Ele gera embeddings de 128 números, e a

comparação usa similaridade de cosseno com um limite configurável. O

arquivo do modelo e a sua versão ficam fixados no projeto.







\## Status







Aceita.







\## Consequências







\- A licença Apache 2.0 permite uso comercial.

\- A precisão publicada na base LFW é de 99,40%, praticamente igual à do

&#x20; dlib (99,38%), com instalação mais simples.

\- Os modelos pré-treinados do InsightFace ficam de fora, porque são

&#x20; liberados apenas para pesquisa não comercial.

\- A precisão na LFW mede pares de imagens, e não a busca de uma pessoa

&#x20; entre muitas; o limite de semelhança precisa ser calibrado com imagens

&#x20; de teste próprias. O valor publicado (0,363) é só o ponto de partida.

\- O OpenCV não informa com quais dados o SFace foi treinado, o que merece

&#x20; avaliação antes de uso real.

\- Trocar de modelo exige recalcular os embeddings de todas as pessoas.



