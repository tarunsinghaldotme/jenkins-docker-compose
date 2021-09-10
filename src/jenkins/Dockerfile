FROM jenkins/jenkins:lts
USER root
RUN apt-get update && apt-get install -y software-properties-common
RUN apt-get install python python-pip -y
RUN apt-get update
RUN pip install yq 
#RUN apt-get install awscli -y
RUN apt-get install jq -y
RUN apt-get install sudo
RUN mkdir -p /tmp/download && curl -L https://download.docker.com/linux/static/stable/x86_64/docker-20.10.8.tgz | tar -xz -C /tmp/download && rm -rf /tmp/download/docker/dockerd && mv /tmp/download/docker/docker* /usr/local/bin/ && rm -rf /tmp/download && groupadd -g 999 docker && usermod -aG docker jenkins
RUN apt-get install vim -y
RUN apt-get install zip -y
RUN apt-get install wget curl  -y
RUN apt-get install maven rsync -y
RUN pip install awscli
RUN curl -LO "https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl"
RUN sudo mv ./kubectl /usr/local/bin/kubectl
RUN chmod +x /usr/local/bin/kubectl
RUN curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3
RUN chmod 700 get_helm.sh
RUN ./get_helm.sh
RUN chown -R jenkins:jenkins /var/jenkins_home/
USER jenkins
