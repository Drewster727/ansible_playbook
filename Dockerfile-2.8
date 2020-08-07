FROM alpine:3.8

ENV ANSIBLE_VERSION 2.9.11
ENV ANSIBLE_LINT 3.5.1
ENV DOCKER_PY_VERSION 1.10.6
ENV PACKER_VERSION 1.6.1

RUN apk add --update python py-pip openssl ca-certificates bash git sudo zip tar \
    && apk --update add --virtual build-dependencies python-dev libffi-dev openssl-dev build-base \
    && pip install --upgrade pip cffi \
    && echo "Installing Ansible..." \
    && pip install ansible==$ANSIBLE_VERSION ansible-lint==$ANSIBLE_LINT docker-py==$DOCKER_PY_VERSION \
    && pip install --upgrade pycrypto pywinrm  \
    && apk --update add sshpass openssh-client rsync \
    && echo "Removing package list..." \
    && apk del build-dependencies \
    && rm -rf /var/cache/apk/* \
    && mkdir -p /opt/packer \
    && wget -nc -q https://releases.hashicorp.com/packer/${PACKER_VERSION}/packer_${PACKER_VERSION}_linux_amd64.zip -P /opt/packer \
    && unzip -q /opt/packer/packer_${PACKER_VERSION}_linux_amd64.zip -d /opt/packer

RUN echo "Adding hosts for convenience..." \
    && mkdir -p /etc/ansible \
    && echo 'localhost' > /etc/ansible/hosts

ENV PATH $PATH:/opt/packer
ENV ANSIBLE_GATHERING smart
ENV ANSIBLE_HOST_KEY_CHECKING false
ENV ANSIBLE_RETRY_FILES_ENABLED false
ENV ANSIBLE_SSH_PIPELINING True

ENTRYPOINT ["ansible-playbook"]
