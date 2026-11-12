# Museu do Amanhã: estudo de sol e sombra

Página interativa (three.js) para apresentar o projeto de conforto térmico e luminoso do Museu do Amanhã, Rio de Janeiro.

## Como usar

A página abre com uma tela inicial ("Melhores lugares para uma fresca e um solzinho no Museu do Amanhã") e o botão **Iniciar**. O visual todo é em vidro translúcido.

Abra `index.html` no navegador (o arquivo é autocontido: modelo e fotos estão embutidos; só o three.js vem do CDN jsDelivr). Para publicar, ative o GitHub Pages na branch `main`, pasta raiz.

- **Sol**: controla a hora do dia (0h a 24h, de 5 em 5 minutos), com botão "Meio-dia" e animação do dia. A data é a de hoje (fuso de São Paulo).
- **Fotos**: o 3D continua na tela, com pinos numerados e uma faixa de miniaturas embaixo. Tocar numa miniatura ou num pino aproxima a câmera do pino correspondente e mostra a foto na faixa; "Ampliar foto" abre em tela cheia, com zoom (pinça, toque duplo, roda do mouse, botões + e −) e botão Voltar no topo. Tocar em Fotos de novo esconde pinos e miniaturas.
- **Ajustar posição dos pinos**: botão "Ajustar pinos" na faixa de Fotos. Escolha um pino, toque no piso do modelo, e use "Copiar posições" para guardar as coordenadas.

## Premissas

- **Localização**: lat −22,8944°, lon −43,1797°, fuso UTC−3, sem horário de verão.
- **Posição do sol**: algoritmo da NOAA (equação do tempo, declinação, refração atmosférica).
- **Norte verdadeiro**: a ponta do píer aponta para 30° (NNE). É uma estimativa a partir do eixo do Píer Mauá, **não verificada em imagem de satélite**. Para alterar, mude `north:30` no objeto `state` dentro de `index.html`.
- **Modelo**: o `.dae` original (SketchUp, 7,2 MB, sem texturas) foi convertido para GLB com compressão meshopt (1,3 MB), com as palmeiras simplificadas. O espelho d'água retangular atrás do disco foi removido (não existe) e coberto com piso.
- **Posições dos pinos**: estimadas, ainda precisam de conferência.

## Arquivos

- `index.html`: página completa.
- `modelo/MuseudoAmanha.dae`: modelo original.
- `modelo/museu-otimizado.glb`: modelo convertido e comprimido (já embutido em `index.html`).
