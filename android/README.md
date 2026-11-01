# HomeSync para Android

Instalado pelo APK (fora da Play Store). O app verifica se há versão nova, avisa, baixa o APK e o
Android pede a confirmação para instalar. Na primeira atualização, o Android também pede para
permitir que o HomeSync instale apps.

## Como instalar

Baixe o `HomeSync-X.Y.Z.apk` do release `android-v…` mais recente em
[Releases](https://github.com/Gustavo-H/HomeSync-releases/releases) e abra no telefone.

## Cada release (tag `android-vX.Y.Z`)

| Arquivo | Para quê |
|---|---|
| `HomeSync-X.Y.Z.apk` | O app, assinado sempre com a **mesma chave** (com outra chave o Android recusa a atualização) |

## Como o app encontra a versão nova

O app lê o [`latest.json`](latest.json) desta pasta, pelo endereço:

```
https://raw.githubusercontent.com/Gustavo-H/HomeSync-releases/main/android/latest.json
```

Formato:

```json
{
  "version": "1.0.0",
  "versionCode": 2,
  "apkUrl": "https://github.com/Gustavo-H/HomeSync-releases/releases/download/android-v1.0.0/HomeSync-1.0.0.apk",
  "sha256": "hash do APK, para o app conferir o download",
  "publishedAt": "2026-11-01",
  "notes": "Resumo do que mudou, mostrado no aviso de atualização."
}
```

- O app compara o `versionCode` com o seu: só um número **maior** é tratado como atualização.
- O `latest.json` só é atualizado **depois** que o APK já está anexado ao release, para o link
  nunca apontar para um arquivo que ainda não existe.
- Enquanto não houver `latest.json`, o app entende que não há atualização.

## Se o app for para a Play Store

A Play Store cuida das atualizações e não permite que o app se atualize por conta própria. Nesse
caso, a versão da loja deixa de consultar esta pasta, e ela fica só para quem instala pelo APK.

Notas de cada versão: [CHANGELOG.md](CHANGELOG.md).
