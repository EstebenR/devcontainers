FROM node:24-trixie-slim
# Possibly move to node:24-slim

# Rojo port
EXPOSE 34872

#Uncomment to enable verbose npm logs
#ENV NPM_CONFIG_LOGLEVEL=info

#For installing global npm dependencies (nevermore)
ENV NPM_CONFIG_PREFIX=/home/node/.npm-global
ENV PATH=$PATH:/home/node/.npm-global/bin 
# optionally if you want to run npm global bin without specifying path

# Update and install dependencies 
RUN apt-get update && apt-get install -y \
    curl \
    unzip \
    libdbus-1-3 \
    git \
    && rm -rf /var/lib/apt/lists/*

# Install Rokit
RUN curl -sSf https://raw.githubusercontent.com/rojo-rbx/rokit/main/scripts/install.sh | bash

# Install Pesde
COPY installPesde.sh /tmp/installPesde.sh
RUN chmod +x /tmp/installPesde.sh && bash -c '/tmp/installPesde.sh'
ENV PATH="${PATH}:/root/.pesde/bin"

# Install Nevermore
RUN npm install -g @quenty/nevermore-cli

# Install Luau lsp ver 1.46 by Quenty, use a temp rokit project for it
RUN mkdir /tmp/rokit && cd /tmp/rokit/ && rokit init && rokit add Quenty/luau-lsp@1.46.0-quenty
