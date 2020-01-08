# BASH New System Setup

## Create dirs for git aware prompt and Vundle
### mkdir ~/.bash
### mkidir -p ~/.vim/bundle

## Clone git aware prompt
git clone git://github.com/jimeh/git-aware-prompt.git ~/.bash

## Install virtualenv and virtualenvwrapper
(Lately I've been using pytho3's built-in venv)
pip install virtualenv
pip install virtualenvwrapper

## Install Vundle
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim

## Setup gitaware prompt bash config
echo "export GITAWAREPROMPT=~/.bash/git-aware-prompt" >> ~/.bashrc
echo "${GITAWAREPROMPT}/main.sh" >> ~/.bashrc
echo "export PS1="\${debian_chroot:+(\$debian_chroot)}\u@\h:\w
\[$txtcyn\]\$git_branch\[$txtred\]\$git_dirty\[$txtrst\]\$ \"" >> ~/.bashrc

## Setup virtualenvwrapper 
echo "export WORKON_HOME=\"$HOME/.virtualenvs\"" >> ~/.bashrc 
echo "source /usr/local/bin/virtualenvwrapper.sh" >> ~/.bashrc

## Install Vim Plugins
vim +PluginInstall +qall


