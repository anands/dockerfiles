FROM ubuntu:18.04

# Essentials
RUN \
    apt-get update && \
    apt-get install -y build-essential checkinstall xz-utils zsh curl wget htop vim git zip unzip

# Install Python:
RUN \
    apt-get install -y python2.7 python-pip

# Node.JS:
RUN \
    curl -sL https://deb.nodesource.com/setup_8.x -o nodesource_setup.sh && \
    chmod +x nodesource_setup.sh && \
    ./nodesource_setup.sh && \
    apt-get install nodejs

# MISC:
RUN \
    # Oh-My-Zsh
    cd ~ && \
    wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | zsh || true && \
    chsh -s /bin/zsh && \
    # VIMRC
    git clone --depth=1 https://github.com/amix/vimrc.git ~/.vim_runtime && \
    sh ~/.vim_runtime/install_awesome_vimrc.sh

CMD ["zsh"]