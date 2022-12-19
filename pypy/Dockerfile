FROM oraclelinux:7

RUN yum install -y which 
RUN yum install -y vim 
RUN yum install -y gcc zlib-devel bzip2 bzip2-devel readline readline-devel sqlite sqlite-devel openssl openssl-devel git libffi-devel
RUN yum install -y libxslt-devel libxml2-devel
RUN git clone https://github.com/pyenv/pyenv.git ~/.pyenv

RUN echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
RUN echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
RUN echo 'eval "$(pyenv init --path)"' >> ~/.bashrc
RUN echo 'eval "$(pyenv init -)"' >> ~/.bashrc
RUN $HOME/.pyenv/bin/pyenv install pypy3.8-7.3.7
RUN $HOME/.pyenv/bin/pyenv global pypy3.8-7.3.7
RUN $HOME/.pyenv/bin/pyenv rehash

RUN yum install -y oracle-nodejs-release-el7 oracle-release-el7
RUN yum install -y nodejs

RUN /root/.pyenv/versions/pypy3.8-7.3.7/bin/python -m pip install --upgrade pip
RUN /root/.pyenv/versions/pypy3.8-7.3.7/bin/python -m pip install online-judge-tools
RUN npm install -g atcoder-cli

RUN acc config-dir
RUN sed -i 's/""/"\/root\/.pyenv\/shims\/oj"/g' /root/.config/atcoder-cli-nodejs/config.json
RUN sed -i 's/"default-template.*/"default-template": "\/root\/.config\/atcoder-cli-nodejs\/python"/g'  /root/.config/atcoder-cli-nodejs/config.json

RUN echo "alias accl='acc login'" >> /root/.bashrc
RUN echo "alias accspypy='acc s main.py -- --guess-python-interpreter pypy'" >> /root/.bashrc
RUN echo "alias ojl='oj login https://atcoder.jp/'" >> /root/.bashrc
RUN echo "set -o vi" >> /root/.bashrc

RUN mkdir -p /root/.config/atcoder-cli-nodejs/python/
RUN echo '{"task":{ "program": ["main.py"], "submit": "main.py" }}' > /root/.config/atcoder-cli-nodejs/python/template.json

RUN echo "#S = input()"  > /root/.config/atcoder-cli-nodejs/python/main.py
RUN echo "#N = int(input())"  >> /root/.config/atcoder-cli-nodejs/python/main.py
RUN echo "#L=input().split()"  >> /root/.config/atcoder-cli-nodejs/python/main.py
RUN echo "#L=list(map(int, input().split()))"  >> /root/.config/atcoder-cli-nodejs/python/main.py

RUN cd /root
