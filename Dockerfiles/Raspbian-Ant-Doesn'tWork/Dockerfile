########################################################
#                                                      #
#   Install Apache Ant on Raspbian                     #
#                                                      #
########################################################

# Set Base Image to Raspbian Java
FROM raspbian-java:latest

# Set Metadata
LABEL OS=Raspbian-Jessie Version=0.1.0

# Environment 
ENV ANT_HOME="/opt/ant/" \
    PATH=$PATH:$ANT_HOME/bin 

RUN mkdir -p /opt/ant && \
chown root:root /opt/ant

# Add Files to Container
COPY apache-ant-1.10.1/ /opt/ant


# Change Permission
RUN chown root:root -R /opt/ant/ && \
chmod u+x -R /opt/ant/ 
