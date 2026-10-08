<!-- versao: 0.5.11-hml.6 -->
# Dukk Homolog 0.5.11-hml.6

Versão de **homologação** do Dukk Enterprise: fala com `dukk.homolog.dukk.com.br` (os PRs abertos do dukk-code e do Enterprise), entra com o mesmo login de sempre e instala **ao lado** do Dukk normal, com pasta de dados própria.

| Sistema | Instalador |
|---|---|
| **macOS (Intel e Apple Silicon)** | ainda em build… |
| **Windows 10/11** | [Dukk-Homolog-0.5.11-hml.6-windows-setup.exe](https://github.com/nextlw/dukk-releases/releases/download/homolog-v0.5.11-hml.6-windows/Dukk-Homolog-0.5.11-hml.6-windows-setup.exe) |
| **Linux (x86-64)** | ainda em build… |

## Avisos ao abrir (instaladores sem assinatura)

- **macOS:** abra o `.dmg` e arraste o *Dukk Homolog* para *Aplicativos*. Na primeira abertura o macOS bloqueia. Vá em **Ajustes do Sistema → Privacidade e Segurança**, role até o aviso do *Dukk Homolog* e clique **Abrir Mesmo Assim**. Ou, no Terminal: `xattr -dr com.apple.quarantine "/Applications/Dukk Homolog.app"`.
- **Windows:** no SmartScreen, **Mais informações → Executar assim mesmo**. Instala em `%LOCALAPPDATA%\Programs\Dukk Homolog`.
- **Linux:** extraia numa pasta própria e rode `./Dukk`. Requer `webkit2gtk-4.1` e `gtk3`.

O app de homolog só se atualiza por este canal (`canal/latest.json` deste branch) e **nunca** chega a quem usa o Dukk normal.

Todas as versões de homolog: [pré-releases](https://github.com/nextlw/dukk-releases/releases).
