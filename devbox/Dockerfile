FROM debian:unstable
MAINTAINER Loïc Frering <loic.frering@gmail.com>

# Install common packages
RUN apt-get update && \
    apt-get install -y --no-install-recommends ca-certificates curl sudo

# Install Zsh, Git, Vim and tmux
RUN apt-get install -y --no-install-recommends zsh git vim tmux

# Create my user
RUN useradd loic -p loic -u 1000 -G sudo -s /usr/bin/zsh --create-home
RUN echo '%sudo ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers

# Switch user
USER loic
WORKDIR /home/loic

# Install oh-my-zsh
RUN git clone https://github.com/robbyrussell/oh-my-zsh.git /home/loic/.oh-my-zsh

# Install my dotfiles
RUN git clone https://github.com/loicfrering/dotfiles.git /home/loic/Projects/dotfiles
RUN ln -s /home/loic/Projects/dotfiles/.zshrc \
          /home/loic/Projects/dotfiles/.gitconfig \
          /home/loic/Projects/dotfiles/.vim \
          /home/loic/Projects/dotfiles/.vimrc \
          /home/loic/Projects/dotfiles/.tmux.conf \
              /home/loic/

# Zsh as entry point
CMD ["/bin/zsh"]
