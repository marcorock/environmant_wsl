# Defindo a versão do PHP
FROM php:8.2-apache

# Atualiza a lista de pacotes e instala o zsh e git
RUN apt-get update && apt-get install -y zsh git

RUN apt install neofetch -y

# Instala o oh-my-zsh
RUN sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

# Instala o plugin zsh-syntax-highlighting
RUN git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

# Instala o plugin zsh-autosuggestions
RUN git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

# Ativa os plugins no .zshrc
RUN echo "plugins=(git zsh-syntax-highlighting zsh-autosuggestions)" >> ~/.zshrc

# Iniciando o Neofetch sempre que o terminal for chamado
RUN echo "neofetch" >> ~/.zshrc

# Define o zsh como o shell padrão
SHELL ["/bin/zsh", "-c"]

RUN zsh --version