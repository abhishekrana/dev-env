FROM ubuntu:18.04

ENV LC_ALL=C.UTF-8
ENV LANG=C.UTF-8

### General packages ###
ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get -y install --no-install-recommends \
	python3-pip \
	git \
	locate \
	&& pip3 install --no-cache-dir --upgrade pip setuptools wheel \
	&& apt-get autoremove -y \
	&& apt-get clean -y \
	&& rm -rf /var/lib/apt/lists/* \
ENV DEBIAN_FRONTEND=dialog

### General pip packages ###
RUN pip3 --no-cache-dir install \
	numpy

### Dev enviroment ###
RUN pip3 --no-cache-dir install \
	black \
	flake8 \
	MonkeyType \
	mypy \
	pudb \
	pycodestyle \
	pydocstyle \
	pylint \
	typeguard
RUN apt-get update && apt-get install -y locales && rm -rf /var/lib/apt/lists/*
RUN locale-gen en_US.UTF-8

RUN updatedb

