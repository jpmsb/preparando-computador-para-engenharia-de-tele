# Docker

## Instalação

Como o openSUSE Tumbleweed é uma distribuição de lançamento contínuo, a versão do pacote do Docker presente nos repositórios oficiais costuma acompanhar a mais recente. Para instalar o Docker, juntamente com o Docker Compose, basta executar o comando:

```bash
sudo zypper install docker docker-compose
```

**Caso ocorra erro, atualize a lista de pacotes com o comando abaixo e execute o comando acima novamente**:

```bash
sudo zypper refresh -f
```

Em seguida, inicialize o serviço do Docker:

```bash
sudo systemctl start docker
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

Caso queira que o serviço do Docker seja iniciado junto com o sistema, execute:

```bash
sudo systemctl enable docker
```

**Observação**: Caso o serviço do Docker não seja habilitado para iniciar junto com o sistema, será necessário inicializá-lo manualmente sempre que o seu computador for reiniciado.

## Desinstalação

Para desinstalar o Docker e o Docker Compose, execute:

```bash
sudo zypper remove -u docker docker-compose
```