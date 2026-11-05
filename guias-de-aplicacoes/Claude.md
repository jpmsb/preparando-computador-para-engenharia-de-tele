# Claude

O Claude Desktop é o aplicativo da Anthropic para usar o Claude no computador, com chat, Claude Code e Cowork. No Linux, o suporte oficial está em *beta* e o pacote publicado pela Anthropic é um `.deb` para Ubuntu e Debian. O *script* deste repositório adapta a instalação ao Tumbleweed extraindo o aplicativo desse pacote.

### Tabela de conteúdos

  - [Instalação e atualização](#instalação-e-atualização)
  - [Desinstalação](#desinstalação)

## Instalação e atualização

Para facilitar a instalação e atualização, foi criado um *script* que automatiza o processo, de forma que, com um simples comando, o aplicativo é instalado ou atualizado.

Para instalar ou atualizar o Claude Desktop, execute o seguinte comando:

```bash
curl -sL https://github.com/jpmsb/preparando-computador-para-engenharia-de-tele/raw/main/scripts-auxiliares/instalar-claude | bash
```

Será perguntado pela senha do seu usuário para prosseguir a instalação. Após o aplicativo ter sido instalado, você pode abri-lo digitando `claude-desktop` no terminal ou pelo menu de aplicativos.

<details>
<summary>Observações</summary>

- O suporte oficial no Linux cobre Ubuntu e Debian. Neste repositório, a instalação no openSUSE é feita extraindo o conteúdo do `.deb` oficial para `/opt/Claude`.
- Recursos do Cowork que usam máquina virtual podem exigir virtualização de hardware (KVM) e pacotes como QEMU/`ovmf`/`virtiofsd` no sistema.

</details>

## Desinstalação

Basta remover os arquivos e diretórios criados pelo *script* de instalação:

```bash
sudo rm -r /opt/Claude /usr/local/bin/claude-desktop /usr/share/applications/claude-desktop.desktop
```
