# HomeSync-releases

Versões publicadas do HomeSync para instalar e atualizar. O código fica nos repositórios privados
(`HomeSync-desktop`, `HomeSync-app`, `HomeSync-server`); aqui ficam só os instaladores e as
informações que os apps consultam para saber se há versão nova.

| Pasta | Plataforma | Tags dos releases | Como atualiza |
|---|---|---|---|
| [`desktop/`](desktop/) | Windows (HomeSync Desktop) | `desktop-v1.2.3` | Automática (Velopack): baixa sozinho e aplica ao reiniciar |
| [`android/`](android/) | Android (app HomeSync) | `android-v1.2.3` | O app avisa, baixa o APK e o Android pede para confirmar |

O servidor (`HomeSync-server`) não é distribuído por aqui: ele é atualizado na máquina onde roda.

## Onde ficam os arquivos

- **Instaladores e pacotes** (`.exe`, `.nupkg`, `.apk`): anexados aos **Releases** do GitHub, um
  release por versão. O GitHub aceita anexos grandes ali, ao contrário dos arquivos do repositório.
- **Nas pastas do repositório**: só texto pequeno, ou seja, as notas de versão (`CHANGELOG.md`) e,
  no Android, o `latest.json` que o app lê para saber a versão mais recente.

O `.gitignore` impede que binários sejam enviados para o repositório por engano.

## Regras

1. **Uma tag por versão, com o prefixo da plataforma**: `desktop-v1.4.0`, `android-v1.4.0`. O
   prefixo é o que separa as duas plataformas nos Releases.
2. **A versão só aumenta.** Cada plataforma segue a própria numeração (`MAJOR.MINOR.PATCH`). Uma
   versão publicada nunca é reaproveitada.
3. **Não apague releases publicados**: os apps instalados podem precisar deles (o desktop usa os
   pacotes anteriores para baixar só a diferença).
4. **Versão com problema se corrige publicando outra**, maior. Não há volta automática.
5. **Releases do desktop são gerados pelo script de publicação** do `HomeSync-desktop`, nunca à
   mão: os arquivos do Velopack precisam estar completos e consistentes.
6. O repositório é **público**: nada de senhas, tokens ou dados de usuários aqui.
