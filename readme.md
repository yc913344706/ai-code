# instruction

this repo is only adapted for [my blog](https://yc913344706.github.io/archives/)

# python install cmds

```shell
# root
apt install build-essential zlib1g-dev libncurses5-dev libgdbm-dev \
    libnss3-dev libssl-dev libreadline-dev libffi-dev wget \
    libsqlite3-dev libbz2-dev graphviz lzma liblzma-dev libbz2-dev

./configure --prefix=/usr/local/src/Python-3.9.16

make -j 30 && make altinstall

/usr/local/src/Python-3.9.16/bin/pip3.9 install virtualenv

# yuchuan
su - yuchuan
cd ~/.e
/usr/local/src/Python-3.9.16/bin/virtualenv jupyter
source /home/yuchuan/.e/jupyter/bin/activate

cd ~/.a/ai-code
pip install -r requirements.txt

jupyter notebook --ip=192.168.10.48 --port=58330
```