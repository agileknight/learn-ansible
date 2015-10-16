FROM williamyeh/ansible:ubuntu14.04

WORKDIR /ansible

RUN echo localhost > inventory

ADD java8.yml /ansible/
RUN ansible-playbook -T 1 -i inventory java8.yml --connection=local

ADD jetty.yml /ansible/
RUN ansible-playbook -i inventory jetty.yml --connection=local
