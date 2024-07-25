# instruction

this repo is only adapted for [my blog](https://yc913344706.github.io/archives/)

# python install cmds

```shell
# root
mkdir -p ~/yuchuan/.env

cd ~/yuchuan/.env && wget https://www.python.org/ftp/python/3.9.16/Python-3.9.16.tgz && tar -xf Python-3.9.16.tgz && cd Python-3.9.16

apt install build-essential zlib1g-dev libncurses5-dev libgdbm-dev \
    libnss3-dev libssl-dev libreadline-dev libffi-dev wget \
    libsqlite3-dev libbz2-dev graphviz lzma liblzma-dev libbz2-dev

./configure --prefix=/usr/local/src/Python-3.9.16
make -j 30 && make altinstall

pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
/usr/local/src/Python-3.9.16/bin/pip3.9 install virtualenv

# yuchuan
su - yuchuan
mkdir -p ~/.e ~/.a
cd ~/.e && /usr/local/src/Python-3.9.16/bin/virtualenv jupyter
source /home/yuchuan/.e/jupyter/bin/activate

cd ~/.a && git clone git@github.com:yc913344706/ai-code.git
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
cd ~/.a/ai-code
pip install -r requirements.txt

export LD_PRELOAD="/home/yuchuan/.e/jupyter/lib/python3.9/site-packages/nvidia/nvjitlink/lib/libnvJitLink.so.12"
jupyter notebook --ip=0.0.0.0 --port=58330
```