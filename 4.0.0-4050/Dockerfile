#
# Couchbase Test
#
FROM ubuntu:12.04
MAINTAINER 	Corbin Uselton <corbinu@decimal.io>

# Install dependencies
RUN apt-get update && \
    apt-get install -yq runit wget python-httplib2  && \
    apt-get autoremove && apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

COPY couchbase-server-enterprise_4.0.0-4050-ubuntu12.04_amd64.deb .

RUN dpkg -i couchbase-server-enterprise_4.0.0-4050-ubuntu12.04_amd64.deb && \
        rm -f couchbase-server-enterprise_4.0.0-4050-ubuntu12.04_amd64.deb

# Add runit script for couchbase-server
COPY bin/run /etc/service/couchbase-server/run
RUN chmod 755 /etc/service/couchbase-server/run

# Add bootstrap script
COPY bin/entrypoint.sh /

ENV PATH=$PATH:/opt/couchbase/bin:/opt/couchbase/bin/tools:/opt/couchbase/bin/install
ENV CB_USERNAME Administrator
ENV CB_PASSWORD password

COPY bin/* /usr/local/bin/

EXPOSE 8091 8092 11207 11210 11211 18091 18092
VOLUME /opt/couchbase/var

ENTRYPOINT ["/entrypoint.sh"]
CMD ["couchbase-server"]
