FROM debian:12

RUN apt-get update
RUN apt-get install -y git git-lfs
RUN git lfs install

RUN mkdir -p /etc/pterodactyl
RUN curl -L -o /usr/local/bin/wings "https://github.com/pterodactyl/wings/releases/latest/download/wings_linux_$([[ "$(uname -m)" == "x86_64" ]] && echo "amd64" || echo "arm64")"
RUN chmod u+x /usr/local/bin/wings

RUN git clone https://github.com/deckploy/agentd /tmp/agentd
RUN chmod +x /tmp/agentd/agentd
RUN cp /tmp/agentd/agentd /usr/bin/agentd