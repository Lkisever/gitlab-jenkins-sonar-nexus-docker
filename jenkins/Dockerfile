ARG JENKINS_VERSION

# https://github.com/jenkinsci/docker
FROM jenkins/jenkins:${JENKINS_VERSION}
USER root
RUN apt-get update -qq \
    && apt-get install -qqy apt-transport-https ca-certificates curl gnupg2 software-properties-common wget build-essential bzip2 
RUN ssh-keygen -t rsa -N "" -f ~/.ssh/id_rsa
RUN curl -fsSL https://download.docker.com/linux/debian/gpg | apt-key add -
RUN add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/debian \
   $(lsb_release -cs) \
   stable"
RUN apt-get update  -qq \
    && apt-get install docker-ce -y
RUN usermod -aG docker jenkins