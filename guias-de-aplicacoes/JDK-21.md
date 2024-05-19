# JDK (Java Development Kit) 21

## Instalação

Para instalar o JDK 21, basta executar o comando:

```bash
sudo zypper install java-21-openjdk
```

Em seguida, defina a variável de ambiente `JAVA_HOME` com o comando:

```fish
set --export JAVA_HOME (dirname (dirname (readlink -f (which java))))
```

Voc^pode verificar se o JDK foi instalado corretamente com o comando:

```bash
java --version
```

A saída é semelhante à abaixo:

![](imagens/jdk_21_version.png)