########################################################
#                                                      #
#   Install Oracle JDK 1.8 on Raspbian                 #
#                                                      #
########################################################

# Set Base Image to Raspbian Jessie
FROM resin/rpi-raspbian:wheezy-20170913

# Set Metadata
LABEL OS=Raspbian-Jessie Version=0.1.0

# Environment 
ENV JAVA_HOME="/opt/java/jdk1.8.0_144" \
    PATH=$PATH:$JAVA_HOME/bin 

RUN mkdir -p /opt/java && \
chown root:root /opt/java

# Add Files to Container
COPY jdk-8u144-linux-arm32-vfp-hflt.tar.gz /opt/java


# Change Permission
RUN chmod u+x /opt/java/jdk-8u144-linux-arm32-vfp-hflt.tar.gz && \

# Unzip
cd /opt/java && \
tar -zxvf /opt/java/jdk-8u144-linux-arm32-vfp-hflt.tar.gz && \
rm /opt/java/jdk-8u144-linux-arm32-vfp-hflt.tar.gz && \

# Install Java 1.8
update-alternatives --install "/usr/bin/java" "java" "/opt/java/jdk1.8.0_144/bin/java" 1 && \
update-alternatives --set java /opt/java/jdk1.8.0_144/bin/java 