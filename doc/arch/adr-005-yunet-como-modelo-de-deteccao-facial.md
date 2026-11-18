\# ADR 005: YuNet como modelo de detecção facial



\## Contexto



Antes de reconhecer alguém, o projeto precisa encontrar o rosto na imagem

e os pontos usados para alinhá-lo. A detecção roda ao vivo, quadro a

quadro, inclusive em aparelhos com pouco poder de processamento. Foram

considerados o YuNet (OpenCV Zoo), os detectores do dlib e o SCRFD.



\## Decisão



O YuNet, distribuído pelo OpenCV Zoo em formato ONNX, na versão de 2023,

é o modelo de detecção facial do projeto. Ele roda pelo OpenCV 4.8 ou

posterior, na série 4.x, e fornece os cinco pontos do rosto usados no

alinhamento. O arquivo do modelo e a sua versão ficam fixados no projeto.



\## Status



Aceita.



\## Consequências



\- A licença é permissiva (MIT, segundo o OpenCV Zoo) e permite uso

&#x20; comercial.

\- O modelo é leve e rápido: cerca de 1,5 ms por imagem pequena numa CPU

&#x20; Intel, segundo o próprio OpenCV Zoo, o que permite detecção ao vivo.

\- O SCRFD é mais preciso, mas é mais pesado e vem do InsightFace, cujos

&#x20; modelos são liberados apenas para pesquisa não comercial.

\- Rostos muito pequenos ou muito grandes na imagem podem não ser

&#x20; detectados, então a câmera precisa enquadrar bem a pessoa.

\- O OpenCV 5.x exige outra variante do YuNet; trocar de série do OpenCV

&#x20; exige revisar esta decisão.

\- O desempenho precisa ser medido no aparelho onde a detecção vai rodar.

