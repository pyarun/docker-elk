ARG ELK_VERSION

# https://www.docker.elastic.co/
FROM docker.elastic.co/logstash/logstash:${ELK_VERSION}

# Add your logstash plugins setup here
# Example: RUN logstash-plugin install logstash-filter-json


# Install Redli (redis-cli) to be able to collect redis metric
USER root
WORKDIR /tmp
RUN curl -0L https://github.com/IBM-Cloud/redli/releases/download/v0.4.4/redli_0.4.4_linux_amd64.tar.gz --output redli_0.4.4_linux_amd64.tar.gz && \
             tar xvf redli_0.4.4_linux_amd64.tar.gz && mv redli /usr/local/bin/ && rm redli_0.4.4_linux_amd64.tar.gz

# back to origin workdir
USER logstash
WORKDIR /usr/share/logstash