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
