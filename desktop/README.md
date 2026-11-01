# HomeSync Desktop (Windows)

Instalado por usuário (sem administrador) em `%LocalAppData%\HomeSync`, com atualização automática
pelo [Velopack](https://velopack.io). As configurações do app ficam em
`%LocalAppData%\HomeSync Desktop` e sobrevivem às atualizações.

## Como instalar

Baixe o `HomeSync-win-Setup.exe` do release `desktop-v…` mais recente em
[Releases](https://github.com/Gustavo-H/HomeSync-releases/releases) e execute.

Sem certificado de assinatura de código, o Windows mostra "O Windows protegeu o computador" na
primeira instalação: clique em **Mais informações** > **Executar assim mesmo**. As atualizações
seguintes não mostram esse aviso.

## Cada release (tag `desktop-vX.Y.Z`)

Gerado e enviado pelo script de publicação do `HomeSync-desktop` (`vpk pack` + `vpk upload github`):

| Arquivo | Para quê |
|---|---|
| `HomeSync-win-Setup.exe` | Primeira instalação |
| `HomeSync-win-Portable.zip` | Versão portátil: roda de uma pasta, sem instalar |
| `HomeSync-X.Y.Z-full.nupkg` | O app completo (instalações que não podem usar o delta) |
| `HomeSync-X.Y.Z-delta.nupkg` | Só o que mudou desde a versão anterior (download pequeno) |
| `releases.win.json` | Lista de versões que o app consulta |
| `RELEASES` | Arquivo auxiliar do Velopack |

## Como o app encontra a versão nova

A verificação é feita só quando o usuário clica em **Configurações > Atualizações > Verificar
atualizações**. O app lê até 100 releases deste repositório e considera apenas os que têm o
`releases.win.json`, ou seja, os do desktop; os do Android são ignorados. (O leitor padrão do
Velopack só olha os 10 releases mais recentes, o que perderia versões do desktop atrás de vários
releases do Android.)

Notas de cada versão: [CHANGELOG.md](CHANGELOG.md).
