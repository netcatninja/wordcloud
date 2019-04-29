BootStrap: docker
From: ubuntu:18.04

%help
    Install Python 3.6 and make a word cloud

%runscript
    /opt/python3/bin/python3.6 -V
    echo "We are going to make a word cloud."
    echo "Text: $1"
    echo "Image: $2"
    /opt/python3/bin/wordcloud_cli --text $1 --imagefile $2 
    
%environment
    export LC_ALL=en_US.UTF-8
    export LANG=en_US.UTF-8
    export PATH=/opt/python3/bin:/usr/bin:/usr/local/sbin:/bin:/usr/local/bin:/usr/sbin:/sbin

%post
    apt-get -y update && apt-get install -y --no-install-recommends  \
    build-essential ca-certificates git libssl-dev lolcat wget zlib1g-dev
    cd /opt && wget https://www.python.org/ftp/python/3.6.8/Python-3.6.8.tar.xz && \
    tar xf Python-3.6.8.tar.xz && cd Python-3.6.8 && ./configure --prefix=/opt/python3 && \
    make && make altinstall && ln -s /opt/python3/bin/python3.6 /opt/python3/bin/python3
    /opt/python3/bin/pip3.6 install wordcloud

%labels
    Author Brie Carranza
