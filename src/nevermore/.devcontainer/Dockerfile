FROM node:24-trixie-slim
ENV PNPM_HOME="/pnpm"
ENV PATH="$PNPM_HOME:$PATH"
RUN corepack enable
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
RUN pnpm install -g @quenty/nevermore-cli

# Install Luau lsp ver 1.58 by Quenty
RUN /root/.rokit/bin/rokit trust Quenty/luau-lsp && \
    /root/.rokit/bin/rokit add --global Quenty/luau-lsp@1.58.0-quenty.1

# Install latest rojo
RUN /root/.rokit/bin/rokit trust Quenty/rojo && \
    /root/.rokit/bin/rokit add --global Quenty/rojo