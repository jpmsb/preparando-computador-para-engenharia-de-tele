# CLion

O CLion é uma IDE da JetBrains com foco em desenvolvimento C e C++.

## Instalação

Para facilitar a instalação, foi criado um *script* que automatiza o processo, de forma que, com um simples comando, a IDE é instalada.

Para instalar o CLion, execute o seguinte comando:

```bash
curl -sL https://github.com/jpmsb/preparando-computador-para-engenharia-de-tele/raw/main/scripts-auxiliares/instalar-clion | bash
```

Será perguntado pela senha do seu usuário para prosseguir a instalação. Após a IDE ter sido instalada, você pode abri-la digitando `clion` no terminal ou pelo menu de aplicativos em **Menu** &rarr; **Desenvolvimento** &rarr; **CLion**.

![](imagens/opensuse_tumbleweed_clion_menu.png)

## Desinstalação

Basta remover os arquivos e diretórios criados pelo *script* de instalação.

```bash
sudo rm -r /opt/JetBrains/CLion* /usr/share/applications/clion.desktop /usr/local/bin/clion
```