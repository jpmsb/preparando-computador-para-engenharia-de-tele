# MQTT (Mosquitto)

O MQTT (_Message Queuing Telemetry Transport_) é um protocolo de mensagens leves e amplamente utilizado para comunicação entre dispositivos IoT.

## Instanciando um servidor MQTT

Para que fique mais prático, será utilizado contêiner para instanciar o servidor MQTT. Dessa forma, garanta que o [Docker](Docker.md) ou o [Podman](Podman.md) estejam instalados em seu sistema.

### Preparação

Primeiramente, é preciso criar uma estrutura de diretórios inicial para abrigar as configurações, os dados e os logs da aplicação. Recomenda-se que esse diretório seja criado em um local que seja conveniente. No exemplo abaixo, será criado um diretório para armazenar dados de contêineres. Dessa forma, adapte o comando abaixo para o seu caso de uso:

```bash
mkdir -p ~/containers/mosquitto/data ~/containers/mosquitto/config ~/containers/mosquitto/log
```

No exemplo acima:

- `~/containers/mosquitto/data`: Diretório para armazenar os dados do servidor MQTT;
- `~/containers/mosquitto/config`: Diretório para armazenar os arquivos de configuração do servidor MQTT;
- `~/containers/mosquitto/log`: Diretório para armazenar os logs do servidor MQTT.

Em seguida, crie um arquivo de configuração em `~/containers/mosquitto/config/mosquitto.conf` com o seguinte conteúdo inicial:

```bash
listener 1883
allow_anonymous false
```

Caso queira adicionar autenticação, basta criar um arquivo de senhas, que pode ser gerenciado com o comando `mosquitto_passwd`, que é encontado no pacote `mosquitto`:

```bash
sudo zypper install mosquitto
```

Abaixo, é apresentado um exemplo de como criar um arquivo de senhas:

```bash
mosquitto_passwd -c ~/containers/mosquitto/config/passwd "usuário"
```

Será perguntado para criar a senha do usuário. Após isso, adicione o seguinte conteúdo ao arquivo de configuração:

```bash
password_file /mosquitto/config/passwd
```

Dessa forma, o arquivo de configuração deste exemplo ficará da seguinte forma:

```bash
listener 1883
allow_anonymous false
password_file /mosquitto/config/passwd
```

**Note que o arquivo de senhas em si foi criado em `~/containers/mosquitto/config/passwd`, mas o caminho informado no arquivo de configuração é `/mosquitto/config/passwd`. Isso ocorre porque o diretório `~/containers/mosquitto/config` será montado em `/mosquitto/config` dentro do contêiner.**

### Instanciação

A imagem utilizada para instanciar o servidor MQTT será a `eclipse-mosquitto`. Para instanciar o servidor MQTT, execute o seguinte comando:

- Docker

```bash
docker run -d --name mosquitto -p 1883:1883 -v ~/containers/mosquitto/config:/mosquitto/config -v ~/containers/mosquitto/data:/mosquitto/data -v ~/containers/mosquitto/log:/mosquitto/log eclipse-mosquitto
```

- Podman

```bash
podman run -d --name mosquitto -p 1883:1883 -v ~/containers/mosquitto/config:/mosquitto/config -v ~/containers/mosquitto/data:/mosquitto/data -v ~/containers/mosquitto/log:/mosquitto/log eclipse-mosquitto
```

Abaixo, está um quadro com alguns comandos úteis para gerenciar o contêiner:

| Descrição                       | Comando Docker             | Comando Podman             |
|---------------------------------|----------------------------|----------------------------|
| Parar o contêiner               | `docker stop mosquitto`    | `podman stop mosquitto`    |
| Iniciar o contêiner             | `docker start mosquitto`   | `podman start mosquitto`   |
| Reiniciar o contêiner           | `docker restart mosquitto` | `podman restart mosquitto` |
| Remover o contêiner             | `docker rm mosquitto`      | `podman rm mosquitto`      |
| Visualizar os logs do contêiner | `docker logs mosquitto`    | `podman logs mosquitto`    |

## Instalação dos clientes MQTT

Para instalar os clientes MQTT, execute o seguinte comando:

```bash
sudo zypper install mosquitto-clients
```

### Uso

No pacote instalado, são disponibilizados os seguintes clientes MQTT:

- `mosquitto_pub`: Utilizado para publicar mensagens em um tópico MQTT;
- `mosquitto_sub`: Utilizado para se inscrever em um tópico MQTT e receber mensagens;
- `mosquitto_rr`: Utilizado para publicar mensagens em um tópico MQTT e receber uma resposta.

#### Publicando mensagens

Para publicar uma mensagem em um tópico MQTT, será utilizado o comando `mosquitto_pub`. Abaixo, são apresentados alguns exemplos de uso:

- Publicar uma mensagem sem autenticação:

```bash
mosquitto_pub -h "endereço do servidor" -t "tópico" -m "mensagem"
```

- Publicar uma mensagem com autenticação:

```bash
mosquitto_pub -h "endereço do servidor" -t "tópico" -m "mensagem" -u "usuário" -P "senha"
```

- Para especificar a porta do servidor MQTT:

```bash
mosquitto_pub -h "endereço do servidor" -p "porta" -t "tópico" -m "mensagem"
```

- Publicar em um sub-tópico:

```bash
mosquitto_pub -h "endereço do servidor" -t "tópico/sub-tópico" -m "mensagem"
```

#### Recebendo mensagens

Para se inscrever em um tópico MQTT e receber mensagens, será utilizado o comando `mosquitto_sub`. Este comando ficará recebendo mensagens indefinidamente até que seja interrompido. Abaixo, são apresentados alguns exemplos de uso:

- Receber mensagens de um servidor que não requer autenticação:

```bash
mosquitto_sub -h "endereço do servidor" -t "tópico"
```

- Receber mensagens de um servidor que requer autenticação:

```bash
mosquitto_sub -h "endereço do servidor" -t "tópico" -u "usuário" -P "senha"
```

- Para especificar a porta do servidor MQTT:

```bash
mosquitto_sub -h "endereço do servidor" -p "porta" -t "tópico"
```

- Receber mensagens de um sub-tópico:

```bash
mosquitto_sub -h "endereço do servidor" -t "tópico/sub-tópico"
```

### Desinstalação

Para desinstalar o pacote com os clientes MQTT, execute o seguinte comando:

```bash
sudo zypper remove -u mosquitto-clients
```