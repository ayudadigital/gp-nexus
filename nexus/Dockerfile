FROM sonatype/nexus3:3.22.1

# Packages
USER root
RUN yum install --disableplugin=subscription-manager -y rsync && \
    yum --disableplugin=subscription-manager clean all

# Copy backup/cleanup scripts
COPY backup /usr/local/bin/backup
COPY cleanup /usr/local/bin/cleanup

# GP service identification
RUN echo "nexus" > /gp.service

# Change to the nexus user
USER nexus
