# neovim in a container

FROM alpine:latest

LABEL maintainer "Muhammad Hannan <me@hnnazm.com>"

WORKDIR /root

ENV PATH=$PATH:/root/go/bin

RUN apk --no-cache add \
neovim \
git \
nodejs \
npm \
python3 \
py3-pip \
rust \
rust-analyzer \
cargo \
ccls \
g++ \
make \
go

RUN npm install -g \
neovim \
typescript \
typescript-language-server \
vscode-langservers-extracted

RUN pip install \
jedi-language-server

RUN go install golang.org/x/tools/gopls@latest

RUN git clone https://github.com/hnnazm/.vim.git \
&& ln -sf ./.vim/vimrc .vimrc \
&& mkdir -p ~/.config/nvim \
&& ln -snf ~/.vim/init.vim ~/.config/nvim/init.vim \
&& nvim +PlugInstall +qall 

CMD [ "nvim" ]
