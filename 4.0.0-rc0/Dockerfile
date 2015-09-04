#
# Couchbase Test
#
FROM 		couchbase/server:enterprise-4.0.0-3508
MAINTAINER 	Corbin Uselton <corbinu@decimal.io>

ENV CB_USERNAME Administrator
ENV CB_PASSWORD password

COPY bin/* /usr/local/bin/

EXPOSE 8091 8092 11207 11210 11211 18091 18092
VOLUME /opt/couchbase/var

ENTRYPOINT ["/entrypoint.sh"]
CMD ["couchbase-server"]
