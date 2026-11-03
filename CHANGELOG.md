# Notas de versão

Mais recente primeiro, separado por plataforma. Cada versão corresponde a um release
(`desktop-vX.Y.Z` ou `android-vX.Y.Z`).

<!--
### X.Y.Z — DD/MM/AAAA

- O que mudou, em linguagem do usuário.
- Requer HomeSync-server de DD/MM/AAAA ou mais novo (quando for o caso).
-->

## Windows (HomeSync Desktop)

### 1.0.4 — 03/11/2026

- Tela Servidor mostra a versão da API.
- Temperaturas: o segundo HD aparece como **HD de backup** (o do sistema, quando o servidor o
  informa, aparece separado).
- Mensagens mais curtas ao baixar e instalar uma atualização do desktop.
- Versão da API e HD do sistema: requer o HomeSync-server 1.0.1.

### 1.0.3 — 02/11/2026

- Tela Servidor: card **Temperaturas**, ao vivo, com o processador, o gabinete e os HDs, cada um
  com um indicador verde, amarelo ou vermelho.
- Atualização do servidor acompanhada até o fim: fila, reconstrução e servidor reiniciando, e no
  final o resultado (atualizado, voltou para a versão anterior ou falhou), com "Ver registro". Ao
  abrir a tela, aparece o resultado da última atualização.
- Requer o HomeSync-server de 02/11/2026 ou mais novo, com o atualizador instalado
  (`deploy/install-updater.sh`); com um servidor mais antigo, o card avisa para atualizá-lo.

### 1.0.2 — 01/11/2026

- Filtro por dia e trilha clicável dos filtros aplicados (tela > tipo > ano > mês > dia).
- Painel de detalhes com largura ajustável (arrastando a borda), botão "Ampliar" e vídeos
  tocando no próprio painel.
- Selecionar arrastando mostra as marcações de seleção.
- Tela Servidor: card para pedir a atualização do servidor.
- Requer o HomeSync-server com o filtro por dia (dev de 01/11/2026).

### 1.0.1 — 01/11/2026

- Corrige a versão instalada que fechava ao abrir (faltavam os arquivos da interface no pacote).
  Quem instalou a 1.0.0 precisa baixar e executar o instalador da 1.0.1, pois a 1.0.0 não abre
  para se atualizar sozinha.

### 1.0.0 — 01/11/2026

Primeira versão instalável. **Não abre depois de instalada; use a 1.0.1.**

- Galeria de Imagens, Vídeos, Favoritos e Álbuns, com filtros por data, tipo e nome, seleção,
  visualizador, copiar, baixar, imprimir e favoritar.
- Lixeira com restauração, exclusão definitiva e exclusão automática configurável.
- Envio de fotos e vídeos do PC para o servidor.
- Atualização pelo botão em Configurações > Atualizações.
- Requer o HomeSync-server com álbuns e exclusão automática da lixeira (dev de 01/11/2026).

## Android (app HomeSync)

### 1.0.2 — 03/11/2026

- Sai o menu **Preferências**: as mídias baixadas voltam sempre para o álbum de origem e, quando o
  Android não deixa gravar nele (como nas pastas do WhatsApp), vão para o álbum
  "HomeSync - <pasta de origem>" em Pictures, reaproveitado nos próximos downloads.
- A opção "Álbum HomeSync" (tudo num álbum só) deixou de existir.

### 1.0.1 — 02/11/2026

Primeira versão publicada. Instale baixando o APK pelo celular; as próximas chegam por
**Configurações > Atualizações**.

- Card **Atualizações** em Configurações: verifica só quando tocado, baixa o APK, confere o
  SHA-256 e abre o instalador do Android.
