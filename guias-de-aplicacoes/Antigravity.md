# Antigravity

O Antigravity é a plataforma de desenvolvimento agêntica do Google. Ela inclui o **Antigravity** (Hub / Antigravity 2.0), voltado a fluxos com agentes de IA, e o **Antigravity IDE**, um ambiente de edição baseado em VS Code.

### Tabela de conteúdos

- [Antigravity](#antigravity)
    - [Tabela de conteúdos](#tabela-de-conteúdos)
  - [Instalação e atualização](#instalação-e-atualização)
    - [Antigravity](#antigravity-1)
    - [Antigravity IDE](#antigravity-ide)
  - [Desinstalação](#desinstalação)

## Instalação e atualização

Para facilitar a instalação e atualização, foram criados *scripts* que automatizam o processo, de forma que, com um simples comando, a ferramenta é instalada ou atualizada.

Abaixo, será mostrado como instalar o Antigravity e o Antigravity IDE, podendo ambos serem instalados lado a lado sem problemas.

### Antigravity

Para instalar ou atualizar o Antigravity, execute o seguinte comando:

```bash
curl -sL https://github.com/jpmsb/preparando-computador-para-engenharia-de-tele/raw/main/scripts-auxiliares/instalar-antigravity | bash
```

Será perguntado pela senha do seu usuário para prosseguir a instalação. Após a ferramenta ter sido instalada, você pode abri-la digitando `antigravity` no terminal ou pelo menu de aplicativos em **Menu** &rarr; **Desenvolvimento** &rarr; **Antigravity**.

### Antigravity IDE

Para instalar ou atualizar o Antigravity IDE, execute o seguinte comando:

```bash
curl -sL https://github.com/jpmsb/preparando-computador-para-engenharia-de-tele/raw/main/scripts-auxiliares/instalar-antigravity-ide | bash
```

Será perguntado pela senha do seu usuário para prosseguir a instalação. Após a IDE ter sido instalada, você pode abri-la digitando `antigravity-ide` no terminal ou pelo menu de aplicativos em **Menu** &rarr; **Desenvolvimento** &rarr; **Antigravity IDE**.

## Desinstalação

Para desinstalar o Antigravity e o Antigravity IDE, basta remover os arquivos e diretórios criados pelos *scripts* de instalação.

 - **Antigravity**:

    ```bash
    sudo rm -r /opt/Antigravity /usr/local/bin/antigravity /usr/share/applications/antigravity.desktop
    ```

 - **Antigravity IDE**:

    ```bash
    sudo rm -r /opt/Antigravity-IDE /usr/local/bin/antigravity-ide /usr/share/applications/antigravity-ide.desktop
    ```
