# Octave

O Octave é um software livre para cálculos numéricos, muito utilizado em cursos de engenharia. 

### Tabela de conteúdos

- [Octave](#octave)
    - [Tabela de conteúdos](#tabela-de-conteúdos)
  - [Instalação](#instalação)
    - [Carregando os pacotes na inicialização](#carregando-os-pacotes-na-inicialização)


## Instalação

Para instalar o Octave, bem como os pacotes que serão mais usados ao longo do curso, basta executar o comando:

```bash
sudo zypper install octave octave-cli octave-forge-communications octave-forge-control octave-forge-signal octave-forge-queueing octave-forge-statistics
```

### Carregando os pacotes na inicialização

Para que os pacotes sejam carregados na inicialização do Octave, crie o arquivo `~/.octaverc` com o seguinte comando:

```bash
echo '# Aumentando o tamanho dos textos dos eixos e título
set(0, "defaultaxesfontsize", 16)  % axes labels
set(0, "defaulttextfontsize", 16)  % title

# Carregar pacotes adicionais
pkg load signal
pkg load communications
pkg load statistics
pkg load queueing' > ~/.octaverc
```
