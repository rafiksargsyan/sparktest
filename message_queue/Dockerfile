FROM ubuntu:xenial

RUN apt update

RUN apt install ansible -y
RUN apt install net-tools -y

COPY ansible /ansible
RUN ansible-playbook -i /ansible/local/hosts.ini /ansible/install.yml
COPY entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh

EXPOSE 61600-61700
ENTRYPOINT ["/bin/bash"]
CMD ["/entrypoint.sh", "start"]

