FROM ubuntu:latest 

RUN apt-get update && \
    apt-get install -y \
    curl \
    gnupg \
    jq \ 
    apt-transport-https \
    ca-certificates \
    software-properties-common \
    && rm -rf /var/lib/apt/lists/*

RUN curl -fsSL https://download.docker.com/linux/ubuntu/gpg | apt-key add - && \
    add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" && \
    apt-get update && \
    apt-get install -y docker-ce docker-ce-cli containerd.io

RUN curl -fsSL -o /usr/local/bin/horusec https://github.com/ZupIT/horusec/releases/download/v2.7.0/horusec_linux_amd64 && \
    chmod +x /usr/local/bin/horusec

CMD ["/bin/bash"]