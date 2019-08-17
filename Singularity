Bootstrap: docker
From: nvidia/cuda:10.1-cudnn7-devel-ubuntu18.04

%runscript

    echo "Nothing to do here."

%post

    apt-get update
    apt-get install -y gcc cmake moreutils curl wget git automake autoconf subversion swig build-essential unzip gawk
    apt-get install -y ffmpeg libavc1394-0 libavc1394-dev libsox2 sox libsox-fmt-mp3 libstdc++6 libgomp1 libboost-all-dev zlib1g-dev libbz2-dev liblzma-dev libeigen3-dev libatlas3-base libpulse-dev libssl-dev libffi-dev
    
    apt-get install -y software-properties-common

    add-apt-repository -y ppa:git-core/ppa
    curl -s https://packagecloud.io/install/repositories/github/git-lfs/script.deb.sh | bash

    apt-get install -y  git-lfs
    git lfs install

    apt-get install -y python3 python3-pip python3-venv python3-dev virtualenv

    rm /usr/bin/python && ln -s /usr/bin/python3 /usr/bin/python
    ln -s /usr/bin/pip3 /usr/bin/pip

    apt-get install -y python3-tk
    
    apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y locales
    
    sed -i -e 's/# en_US.UTF-8 UTF-8/en_US.UTF-8 UTF-8/' /etc/locale.gen && \
    dpkg-reconfigure --frontend=noninteractive locales && \
    update-locale LANG=en_US.UTF-8
    
