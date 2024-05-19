# Podman

O Podman é um gerenciador de contêiner que visa ser uma alternativa ao Docker. Uma das diferenças é que o Podman foi projetado para ser executado como usuário não privilegiado, oferecendo mais segurança. Além disso, não opera no modelo cliente/servidor, ou seja, não é necessário um *daemon* rodando em segundo plano para interagir com os contêineres.

## Instalação

Para instalar o Podman juntamente com o `podman compose`, basta executar o comando:

```bash
sudo zypper install podman python311-podman-compose
```

Caso queira disponibilizar o comando `docker` para o Podman, basta instalar o pacote `podman-docker` com o comando:

```bash
sudo zypper install podman-docker
```