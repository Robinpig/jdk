

```shell
wget https://github.com/openjdk/jdk21u/archive/refs/tags/jdk-21.0.5+11.zip
```



Docker
```dockerfile
FROM ubuntu:22.04

RUN apt-get update
RUN apt-get install -y wget unzip
RUN apt-get install -y vim git autoconf make zip libffi-dev build-essential libasound2-dev libcups2-dev libfontconfig1-dev 
RUN apt-get install -y libx11-dev libxext-dev libxrender-dev libxrandr-dev libxtst-dev libxt-dev file
RUN apt-get install -y gdb
RUN apt install -y openjdk-21-jdk

RUN cd /home && wget https://github.com/openjdk/jdk21u/archive/refs/tags/jdk-21.0.5+11.zip
RUN unzip jdk-21.0.5+11.zip && mv jdk21u-jdk-21.0.5-11 jdk21 && cd jdk21

bash configure --with-debug-level=slowdebug --with-jvm-variants=server
make images
```




