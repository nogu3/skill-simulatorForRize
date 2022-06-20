FROM python:3.10.4

# set env
ARG homeDir="/home/src"

# set alias
COPY ./.alias /root
RUN cat /root/.alias >> /root/.bashrc

# update apt-get
RUN apt-get update
RUN apt-get -y install locales && \
    localedef -f UTF-8 -i ja_JP ja_JP.UTF-8

# setup language
ENV LANG ja_JP.UTF-8
ENV LANGUAGE ja_JP:ja
ENV LC_ALL ja_JP.UTF-8
ENV TZ JST-9
ENV TERM xterm

# make srcdir
RUN mkdir -p ${homeDir}
COPY requirements.txt ${homeDir}
WORKDIR ${homeDir}

# python modules update
RUN pip install --upgrade pip
RUN pip install --upgrade setuptools
RUN pip install -r requirements.txt