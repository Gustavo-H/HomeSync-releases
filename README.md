# HomeSync-releases

Versões publicadas do HomeSync. Os arquivos para baixar ficam na aba
**[Releases](https://github.com/Gustavo-H/HomeSync-releases/releases)**, um release por versão; o
código fica nos repositórios privados (`HomeSync-desktop`, `HomeSync-app`, `HomeSync-server`).

## Baixar

| Plataforma | Releases | Arquivo para instalar |
|---|---|---|
| **Windows** (HomeSync Desktop) | [Versões do desktop](https://github.com/Gustavo-H/HomeSync-releases/releases?q=desktop-v&expanded=true) | `HomeSync-win-Setup.exe` (ou `HomeSync-win-Portable.zip`, sem instalar) |
| **Android** (app HomeSync) | [Versões do Android](https://github.com/Gustavo-H/HomeSync-releases/releases?q=android-v&expanded=true) | `HomeSync-X.Y.Z.apk` |

Use sempre o release mais recente da plataforma. O que mudou em cada versão está no
[CHANGELOG.md](CHANGELOG.md) e na descrição de cada release.

**Windows:** sem certificado de assinatura de código, o Windows mostra "O Windows protegeu o
computador" na instalação: clique em **Mais informações** > **Executar assim mesmo**. O app é
instalado só para o usuário (`%LocalAppData%\HomeSync`), sem pedir administrador.

## Como as versões ficam separadas

Cada release tem uma tag com o prefixo da plataforma, e é por ele que os apps acham as suas versões:

| Plataforma | Tag | Arquivos do release | Como o app atualiza |
|---|---|---|---|
| Windows | `desktop-v1.2.3` | `HomeSync-win-Setup.exe`, `HomeSync-win-Portable.zip`, `HomeSync-1.2.3-full.nupkg`, `HomeSync-1.2.3-delta.nupkg`, `releases.win.json`, `RELEASES` | Em **Configurações > Atualizações**, o app procura os releases com o `releases.win.json`, baixa a versão nova (só a diferença, quando possível) e reinicia ([Velopack](https://velopack.io)) |
| Android | `android-v1.2.3` | `HomeSync-1.2.3.apk` | O app procura o release `android-v` mais recente, compara com a versão instalada, baixa o APK (conferindo o hash que o GitHub informa) e o Android pede para confirmar a instalação |

O servidor (`HomeSync-server`) não é distribuído por aqui: ele é atualizado na máquina onde roda.

## Regras para publicar

1. **Uma tag por versão, com o prefixo da plataforma** (`desktop-v1.4.0`, `android-v1.4.0`). Cada
   plataforma segue a própria numeração (`MAJOR.MINOR.PATCH`), que só aumenta.
2. **Windows:** publique sempre pelo script do `HomeSync-desktop`
   (`scripts\publish-release.ps1`), nunca à mão: os arquivos do Velopack precisam estar completos.
3. **Android:** o APK é assinado sempre com a **mesma chave**; com outra, o Android recusa a
   atualização.
4. **Não apague releases publicados que funcionam:** o desktop usa o pacote anterior para baixar só
   a diferença. Uma versão com problema se corrige publicando outra, maior.
5. Registre cada versão no [CHANGELOG.md](CHANGELOG.md).
6. O repositório é **público**: nada de senhas, tokens ou dados de usuários aqui. O `.gitignore`
   impede que instaladores sejam enviados para o código por engano (eles vão nos Releases).
