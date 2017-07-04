FROM dugong/dugong:icewm
MAINTAINER Fabiano Menegidio

USER root

RUN apt-get update \
    && apt-get install graphviz -y \
    && apt-get autoremove -y && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*


WORKDIR /root/

### Install Java Cryptography Extension
RUN curl -v -j -k -L -H "Cookie:oraclelicense=accept-securebackup-cookie" \
    http://download.oracle.com/otn-pub/java/jce/8/jce_policy-8.zip  > jce_policy-8.zip \
    && unzip /root/jce_policy-8.zip \
    && rm /root/jce_policy-8.zip \
    && cp -R /root/UnlimitedJCEPolicyJDK8/* /usr/lib/jvm/java-8-openjdk-amd64/jre/lib/security/ \
    && rm -rf /root/UnlimitedJCEPolicyJDK8/

WORKDIR /root/Desktop
    
### Install Taverna Workbench
RUN wget https://bitbucket.org/taverna/taverna-workbench-product/downloads/taverna-workbench-astronomy-2.5.0-standalone.zip \
    && unzip taverna-workbench-astronomy-2.5.0-standalone.zip \
    && rm taverna-workbench-astronomy-2.5.0-standalone.zip \
    && mv /root/Desktop/taverna-workbench-astronomy-2.5.0/ /root/Desktop/taverna-workbench/ \
    && chmod +x /root/Desktop/taverna-workbench/taverna.sh \
    && cp -R /root/Desktop/taverna-workbench/ $HOME/Desktop/ \
    && chown dugong:dugong $HOME/Desktop/taverna-workbench/
    
 WORKDIR /data
 USER dugong
