# DataGrip

O DataGrip é uma IDE da JetBrains com foco em bancos de dados.

# Instalação

Para facilitar a instalação, foi criado um *script* que automatiza o processo, de forma que, com um simples comando, a IDE é instalada.

Para instalar o DataGrip, execute o seguinte comando:

```bash
curl -sL https://github.com/jpmsb/preparando-computador-para-engenharia-de-tele/raw/main/scripts-auxiliares/instalar-datagrip | bash
```

Será perguntado pela senha do seu usuário para prosseguir a instalação. Após a IDE ter sido instalada, você pode abri-la digitando `datagrip` no terminal ou pelo menu de aplicativos em **Menu** &rarr; **Desenvolvimento** &rarr; **DataGrip**.

![](imagens/opensuse_tumbleweed_datagrip_menu.png)

## Desinstalação

Basta remover os arquivos e diretórios criados pelo *script* de instalação.

```bash
sudo rm -r /opt/JetBrains/DataGrip* /usr/share/applications/datagrip.desktop /usr/local/bin/datagrip
```