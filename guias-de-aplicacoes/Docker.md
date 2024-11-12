# Docker

## Instalação

Como o openSUSE Tumbleweed é uma distribuição de lançamento contínuo, a versão do pacote do Docker presente nos repositórios oficiais costuma acompanhar a mais recente.

Inicialmente, garanta que o sistema está atualizado. Para tal, utilize o comando abaixo:

```bash
atualizar-sistema
```

O comando acima abrirá uma janela de terminal, bastando seguir as instruções exibidas.

Após o processo acima, para instalar o Docker, juntamente com o Docker Compose, execute o comando:

```bash
sudo zypper install docker docker-compose
```

Em seguida, inicialize o serviço do Docker:

```bash
sudo systemctl start docker
```

Caso queira que o serviço do Docker seja iniciado junto com o sistema operacional, execute:

```bash
sudo systemctl enable docker
```

Adicione o seu usuário ao grupo `docker` para que não seja necessário executar comandos com `sudo`:

```bash
sudo usermod -aG docker $USER
```

É preciso reiniciar a sua sessão para que as alterações tenham efeito.

Após o ajustes acima, você pode verificar se o Docker foi instalado corretamente executando:

```bash
docker ps -a
```

**Observação**: Caso o serviço do Docker não seja habilitado para iniciar junto com o sistema, será necessário inicializá-lo manualmente sempre que o seu computador for reiniciado.

## Desinstalação

Para desinstalar o Docker e o Docker Compose, execute:

```bash
sudo zypper remove -u docker docker-compose
```