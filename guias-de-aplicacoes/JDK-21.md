# JDK (Java Development Kit) 21

### Tabela de Conteúdos

- [Instalação](#instalação)
- [Desinstalação](#desinstalação)

## Instalação

Para instalar o JDK 21, basta executar o comando:

```bash
sudo zypper install java-21-openjdk
```

Em seguida, defina a variável de ambiente `JAVA_HOME` com o comando:

```fish
set --export -U JAVA_HOME (dirname (dirname (readlink -f (which java))))
```

Você pode verificar se o JDK foi instalado corretamente com o comando:

```bash
java --version
```

A saída é semelhante à abaixo:

![](imagens/jdk_21_version.png)

## Desinstalação

Para desinstalar o JDK 21 e demais pacotes instalados com o comando acima, execute o comando:

```bash
sudo zypper remove -u java-21-openjdk
```

Para limpar a variável de ambiente `JAVA_HOME`, execute o comando:

```fish
set --erase JAVA_HOME
```