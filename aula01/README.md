# Introdução a Docker - Tutorial
### Docker
Docker é uma plataforma de containerização que permite empacotar aplicações e suas dependências em containers leves e portáveis. Roda sua aplicação já com os requisitos mínimos para funcionamento
### Dockerfile
Um arquivo de texto com uma série de instruções para a montagem de uma imagem para criar o container
### Imagem
Uma imagem é um template somente leitura usado para criar containers.
~~~dockerfile
# ==== Comandos Dockerfile para montagem de imagem (com Fedora) ====

# Usar a imagem base mais recente do Fedora slim e define qual será o SO usado
FROM fedora:latest

# Atualizar o sistema e instalar ferramentas básicas
RUN dnf update -y && \ 
    dnf install -y util-linux procps-ng && \
    dnf clean all

# Define o diretório de trabalho dentro do container
WORKDIR /app

# Comando padrão ao iniciar o container
CMD ["bin/bash"]

# dnf = gerenciador de pacotes exclusivo do Fedora, usado para instalar, atualizar e remover pacotes de software.
# dnf update -y = atualiza todos os pacotes instalados para as versões mais recentes 
# util-linux = instala ferramentas básicas de linha de comando, como fdisk, mount, umount, etc.
# procps-ng = instala ferramentas para monitorar processos, como ps, top, etc.
# dnf clean all = remove cache do gerenciador de pacotes. reduz o tamanho da imagem final
# WORKDIR /app = equivalente a "cd /app"
# CMD ["bin/bash"] = inicia um shell interativo ao iniciar o container
~~~
### Container
Um container é uma instância executável de uma imagem. É um ambiente isolado que contém tudo o que é necessário para executar uma aplicação: código, runtime, ferramentas do sistema, bibliotecas e configurações.
