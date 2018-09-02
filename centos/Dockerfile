FROM centos:latest

RUN \
    yum -y update && \
    yum install -y build-essential checkinstall xz-utils zsh curl wget htop vim git zip unzip && \
    curl https://raw.githubusercontent.com/creationix/nvm/v0.25.0/install.sh | bash && \
    source /root/.bashrc && \
    nvm install node

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