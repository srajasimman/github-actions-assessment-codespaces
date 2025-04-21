FROM mcr.microsoft.com/vscode/devcontainers/universal:linux

# Install nektos/act
RUN curl -s https://raw.githubusercontent.com/nektos/act/master/install.sh | bash

# Additional setup for GitHub Actions testing
RUN apt-get update && apt-get install -y \
    jq \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Install GitHub CLI
RUN curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg \
    && sudo chmod go+r /usr/share/keyrings/githubcli-archive-keyring.gpg \
    && echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
    && sudo apt-get update \
    && sudo apt-get install -y gh

# Create .actrc file for nektos/act configuration
RUN echo "-P ubuntu-latest=ghcr.io/catthehacker/ubuntu:act-latest" > /home/codespace/.actrc && \
    echo "-P ubuntu-22.04=ghcr.io/catthehacker/ubuntu:act-22.04" >> /home/codespace/.actrc && \
    echo "-P ubuntu-20.04=ghcr.io/catthehacker/ubuntu:act-20.04" >> /home/codespace/.actrc && \
    echo "-P ubuntu-18.04=ghcr.io/catthehacker/ubuntu:act-18.04" >> /home/codespace/.actrc && \
    chown codespace:codespace /home/codespace/.actrc

# Setup workspace for assessment
WORKDIR /workspaces