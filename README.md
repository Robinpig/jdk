## Introduction



```shell
wget https://github.com/openjdk/jdk11u/archive/refs/tags/jdk-11.0.25+9.zip

# ubuntu18.04
sudo apt-get install -y vim git autoconf make zip libffi-dev build-essential libasound2-dev libcups2-dev libfontconfig1-dev 
sudo apt-get install -y libx11-dev libxext-dev libxrender-dev libxrandr-dev libxtst-dev libxt-dev 
sudo apt install -y openjdk-11-jdk

bash configure --with-debug-level=slowdebug --with-jvm-variants=server
make images

```
