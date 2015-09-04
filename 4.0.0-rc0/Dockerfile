#
# Couchbase Test
#
FROM 		couchbase/server:enterprise-4.0.0-rc0
MAINTAINER 	Corbin Uselton <corbinu@decimal.io>

ENV CB_USERNAME Administrator
ENV CB_PASSWORD password

COPY bin/* /usr/local/bin/

EXPOSE 8091 8092 11207 11210 11211 18091 18092
VOLUME /opt/couchbase/var

ENTRYPOINT ["couchbase-start"]
CMD ["couchbase-server"]
