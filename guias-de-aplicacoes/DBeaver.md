# DBeaver

O DBeaver é uma ferramenta para trabalhar com banco de dados.

## Instalação

Para instalar o DBeaver, execute o comando abaixo:

```bash
sudo zypper install --allow-unsigned-rpm https://dbeaver.io/files/dbeaver-ce-latest-stable.x86_64.rpm
```

Após a ferramenta ter sido instalada, você pode abri-la digitando `dbeaver` ou `dbeaver-ce` no terminal, ou pelo menu de aplicativos em **Menu** &rarr; **Desenvolvimento** &rarr; **dbeaver-ce**.

![](imagens/opensuse_tumbleweed_dbeaver_menu.png)

## Uso

Quando iniciado pela primeira vez, o tema claro da aplicação pode não ter uma boa harmonia visual com o tema escuro do sistema, ficando semelhante à imagem abaixo:

![](imagens/dbeaver_ce_first_run.png)

Para ajustar o tema, basta ir em no menu "Janela" &rarr; "Preferências":

![](imagens/dbeaver_ce_menu_janela_preferencias.png)

Em seguida, vá em "Interface de usuário" &rarr; "Aparência":

![](imagens/dbeaver_ce_janela_preferencias_aparencia.png)

Em seguida, desmarque a opção "Enable theming":

![](imagens/dbeaver_ce_janela_preferencias_desabilitar_tema.png)

Ao clicar em "Aplicar e Fechar", será solicitado o reinício da aplicação:

![](imagens/dbeaver_ce_reiniciar.png)

Após reiniciado, o DBeaver estará com o tema do sistema:

![](imagens/dbeaver_ce_tema_do_sistema.png)

Alternativamente, é possível utilizar o tema escuro da aplicação. Para tal, vá em "Janela" &rarr; "Preferências" &rarr; "Interface de usuário" &rarr; "Aparência" e selecione o tema "Dark":

![](imagens/dbeaver_ce_tema_dark_selecionado.png)

Ao clicar em "Aplicar e Fechar", será solicitado o reinício da aplicação, bastando clicar em "Reiniciar".

Após reiniciado, o DBeaver estará com o tema escuro próprio:

![](imagens/dbeaver_ce_tema_dark.png)

Outro tema que pode ser usado é o "High Contrast":

![](imagens/dbeaver_ce_tema_high_contrast.png)

Por fim, também possível alterar o tema do sistema para a versão clara, que entra em harmonia com o tema "Light" do DBeaver.

## Desinstalação

Para desinstalar o DBeaver, execute o comando abaixo:

```bash
sudo zypper remove dbeaver-ce
```