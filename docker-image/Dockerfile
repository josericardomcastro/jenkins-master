FROM jenkinsci/blueocean:1.6.2

# Install plugins
# COPY plugins.txt /usr/local/bin/plugins.txt
# RUN /usr/local/bin/install-plugins.sh < /usr/local/bin/plugins.txt

USER root

# configurations
#ENV JAVA_OPTS="-Djenkins.install.runSetupWizard=false"
RUN echo 1.6.2 > /usr/share/jenkins/ref/jenkins.install.UpgradeWizard.state
RUN echo 1.6.2 > /usr/share/jenkins/ref/jenkins.install.InstallUtil.lastExecVersion
COPY groovy-config/* /usr/share/jenkins/ref/init.groovy.d/

# install packages
# RUN apt update
# RUN apt-get install -y maven git openjdk-8-jdk

USER jenkins

# configure jdk
ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64
