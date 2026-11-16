<!-- versao: 0.39.4-hml.242 -->
# Dukk Homolog 0.39.4-hml.242

Versão de **homologação** do Dukk Enterprise: fala com `dukk.homolog.dukk.com.br` (os PRs abertos do dukk-code e do Enterprise), entra com o mesmo login de sempre e instala **ao lado** do Dukk normal, com pasta de dados própria.

| Sistema | Instalador |
|---|---|
| **macOS (Intel e Apple Silicon)** | [Dukk-Homolog-0.39.4-hml.242-macos.dmg](https://github.com/nextlw/dukk-releases/releases/download/homolog-v0.39.4-hml.242-macos/Dukk-Homolog-0.39.4-hml.242-macos.dmg) |
| **Windows 10/11** | [Dukk-Homolog-0.39.4-hml.242-windows-setup.exe](https://github.com/nextlw/dukk-releases/releases/download/homolog-v0.39.4-hml.242-windows/Dukk-Homolog-0.39.4-hml.242-windows-setup.exe) |
| **Linux (x86-64)** | [Dukk-Homolog-0.39.4-hml.242-linux-amd64.tar.gz](https://github.com/nextlw/dukk-releases/releases/download/homolog-v0.39.4-hml.242-linux/Dukk-Homolog-0.39.4-hml.242-linux-amd64.tar.gz) |

## Extensão do VS Code

O painel do Dukk dentro do editor, com o motor de homolog embutido. Baixe o arquivo da sua
plataforma e instale por **painel de extensões → ⋯ → Install from VSIX…**:

| Editor | Arquivo |
|---|---|
| `darwin-arm64` | [dukk-vscode-homolog-darwin-arm64-0.39.4-hml.242.vsix](https://github.com/nextlw/dukk-releases/releases/download/homolog-v0.39.4-hml.242-vscode/dukk-vscode-homolog-darwin-arm64-0.39.4-hml.242.vsix) |
| `darwin-x64` | [dukk-vscode-homolog-darwin-x64-0.39.4-hml.242.vsix](https://github.com/nextlw/dukk-releases/releases/download/homolog-v0.39.4-hml.242-vscode/dukk-vscode-homolog-darwin-x64-0.39.4-hml.242.vsix) |
| `linux-x64` | [dukk-vscode-homolog-linux-x64-0.39.4-hml.242.vsix](https://github.com/nextlw/dukk-releases/releases/download/homolog-v0.39.4-hml.242-vscode/dukk-vscode-homolog-linux-x64-0.39.4-hml.242.vsix) |
| `win32-x64` | [dukk-vscode-homolog-win32-x64-0.39.4-hml.242.vsix](https://github.com/nextlw/dukk-releases/releases/download/homolog-v0.39.4-hml.242-vscode/dukk-vscode-homolog-win32-x64-0.39.4-hml.242.vsix) |

⚠️ **Ela não convive com a "Dukk Code" de produção.** As duas registram os mesmos comandos
(`dukk.*`), e o VS Code só aceita um dono por comando. Desinstale a de produção antes — a
extensão de homolog avisa isso ao abrir, e nunca se instala por cima da outra.

## Avisos ao abrir (instaladores sem assinatura)

- **macOS:** abra o `.dmg` e arraste o *Dukk Homolog* para *Aplicativos*. Na primeira abertura o macOS bloqueia. Vá em **Ajustes do Sistema → Privacidade e Segurança**, role até o aviso do *Dukk Homolog* e clique **Abrir Mesmo Assim**. Ou, no Terminal: `xattr -dr com.apple.quarantine "/Applications/Dukk Homolog.app"`.
- **Windows:** no SmartScreen, **Mais informações → Executar assim mesmo**. Instala em `%LOCALAPPDATA%\Programs\Dukk Homolog`.
- **Linux:** extraia numa pasta própria e rode `./Dukk`. Requer `webkit2gtk-4.1` e `gtk3`.

O app de homolog só se atualiza por este canal (`canal/latest.json` deste branch) e **nunca** chega a quem usa o Dukk normal.

Todas as versões de homolog: [pré-releases](https://github.com/nextlw/dukk-releases/releases).
