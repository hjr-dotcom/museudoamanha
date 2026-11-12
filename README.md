# Museu do Amanhã: estudo de sol e sombra

Página interativa (three.js) para apresentar o projeto de conforto térmico e luminoso do Museu do Amanhã, Rio de Janeiro.

## Como usar

Abra `index.html` no navegador (o arquivo é autocontido: modelo e fotos estão embutidos; só o three.js vem do CDN jsDelivr). Para publicar, ative o GitHub Pages na branch `main`, pasta raiz.

- **Sol**: controla a hora do dia (0h a 24h, de 5 em 5 minutos), com botão "Meio-dia" e animação do dia. A data é a de hoje (fuso de São Paulo).
- **Fotos**: galeria com as 8 fotos do local, com zoom (pinça, toque duplo, roda do mouse, botões + e −). Botão Voltar no topo. Os pinos numerados só aparecem no modelo depois de abrir Fotos (botão "Ocultar pinos" para esconder); tocar num pino abre a foto.
- **Ajustar posição dos pinos**: no fim da tela de Fotos. Escolha um pino, toque no piso do modelo, e use "Copiar posições" para guardar as coordenadas.

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
