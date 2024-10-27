## Introduction

```shell
wget https://github.com/openjdk/jdk8u/archive/refs/tags/jdk8u432-b06.zip

# ubuntu18.04
sudo apt-get install -y vim git autoconf make zip libffi-dev build-essential libasound2-dev libcups2-dev libfontconfig1-dev 
sudo apt-get install -y libx11-dev libxext-dev libxrender-dev libxrandr-dev libxtst-dev libxt-dev 

sudo apt install -y openjdk-8-jdk

bash configure --with-debug-level=slowdebug --with-jvm-variants=server


make images

```
