FROM ubuntu:latest

RUN apt update && apt install -y \
sudo \
git \
python3-pip \
python3.12-venv \
openssh-server
# setting up ssh
RUN ssh-keygen -t ed25519 -C "your_email@example.com" -f /root/.ssh/id_ed25519 -N ""
RUN cp /root/.ssh/id_ed25519.pub ~/.ssh/authorized_keys
RUN /etc/init.d/ssh start
# setting up code
WORKDIR /checkout
RUN git clone -b dockerize-debug https://github.com/pew-x2/openfreemap.git
WORKDIR /checkout/openfreemap
COPY config/env.sample /checkout/openfreemap/config/.env

RUN python3 -m venv py_envs
RUN . /checkout/openfreemap/py_envs/bin/activate && pip install -e .
RUN . /checkout/openfreemap/py_envs/bin/activate && /etc/init.d/ssh start && ./init-server.py http-host-static 127.0.0.1 -y

EXPOSE 80
ENTRYPOINT ["nginx"]
# Provide default arguments to the ENTRYPOINT. The -g daemon off; option keeps
# Nginx running in the foreground, which is necessary for Docker containers.
CMD ["-g", "daemon off;"]
