FROM mcr.microsoft.com/vscode/devcontainers/python:3.8

COPY requirements.txt .devcontainer/resources/* /tmp/resources-tmp/

RUN chmod a+x /tmp/resources-tmp/install.sh && /tmp/resources-tmp/install.sh

RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get install git gcc unzip make -y \
    && pip3 install --disable-pip-version-check --no-cache-dir -r /tmp/resources-tmp/requirements.txt \
    && rm -rf /tmp/resources-tmp
