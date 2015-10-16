FROM ubuntu:14.04

RUN apt-get update && \
    apt-get install --no-install-recommends -y software-properties-common && \
    apt-add-repository ppa:ansible/ansible && \
    apt-get update && \
    apt-get install -y ansible && \
    apt-get clean

RUN echo '[local]\nlocalhost\n' > /etc/ansible/hosts

WORKDIR /ansible

ADD java8.yml /ansible/
RUN ansible-playbook -c local java8.yml

ADD jetty.yml /ansible/
RUN ansible-playbook -c local jetty.yml
