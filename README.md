![alt text](https://api.travis-ci.org/josevictorferreira/klassic.svg?branch=1.0.0)

# klassic - Projeto Inova
  - Projeto da disciplina de Gerência de Configurações
  
# Estruturas das Branchs
  - O projeto está organizado da seguinte forma:
  
     master ->

          v1.0 ->

              dist_1 ->

                  cli_1

                  cli_2

                  cli_3

          v1.1 ->

              dist_2 ->

                  cli_4

          v1.2 ->

              dist_3 ->

                  cli_5

                  cli_6

                  cli_7

                  cli_8

                  cli_9

                  cli_10

              dist_4

              dist_5
              
  - Para atualizar um cliente basta mergir com sua branch pai.

# Dependências
  - Ubuntu 16.04

# Guia de Instalação
  - Instale o git na sua máquina
```bash
  sudo apt update
  sudo apt-get install git
```
  - Clone o repositório
```bash
  git clone https://github.com/josevictorferreira/klassic.git
  cd klassic
```
  - Acesse a branch de desenvolvimento desejada, ex:
```bash
  git checkout 1.0.0
```
## Instalação Expressa
  - Caso desejar utilizar a instalação expressa, execute o arquivo setup.sh para iniciar o script de instalação na sua máquina.
```bash
  sh setup.sh
```

## Docker
  - Caso desejar utilizar o docker, instale a imagem pré-configurada com as principais dependências.
```
  docker build -f Dockerfile -t klassic_container .
```

## Instalação Manual - Passo a Passo - Ubuntu 16.04
  - Instale o java na sua máquina
  ```bash
  sudo apt-get install python-software-properties
  sudo add-apt-repository ppa:webupd8team/java
  sudo apt-get update
  sudo apt-get install oracle-java8-installer
  ```
  - Instale o Maven
```bash
  sudo apt-get install maven
```
  - Instale as dependências do projeto através do maven
```bash
  mvn dependency:go-offline
  mvn install
```
  - Instale o SGBD PostgreSql
```bash
  sudo apt-get install postgresql postgresql-contrib
```
  - Cria a database
```bash
  sudo psql -U postgres -c 'CREATE DATABASE aula;'
```
  - Inicialize o banco
```bash
  sudo psql -U postgres -d aula -a -f Scripts/Database.txt
```
  - Certifique-se que dentro do arquivo `src/main/resources/META-INF/persistence.xml` as propriedades jdbc.user e jdbc.password estejam corretas de acordo com o seu banco de dados.


# Professor
  - Alexandre L'erario

# Alunos
  - José Victor Ferreira
