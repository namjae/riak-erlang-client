RIAK_CONF = ${RIAK_DIR}/etc/riak.conf
ADVANCED_CONF = ${RIAK_DIR}/etc/advanced.config
# RIAK = ${RIAK_DIR}/bin/riak
# RIAK_ADMIN = ${RIAK_DIR}/bin/riak-admin
# CERTS_DIR = $(shell pwd)/../src/test/resources

preconfigure:
	echo "storage_backend = memory" >> ${RIAK_CONF}
	echo "anti_entropy = passive" >> ${RIAK_CONF}
	echo "[{riak_kv,[{test,true}]}]." >> ${ADVANCED_CONF}
	echo "search = on" >> ${RIAK_CONF}
	echo "listener.protobuf.internal = 127.0.0.1:8087" >> ${RIAK_CONF}
	echo "distributed_cookie = riak" >> ${RIAK_CONF}
	echo "nodename = riak@127.0.0.1" >> ${RIAK_CONF}

configure:
	@echo "Nothing to configure on the live node."

compile:
	@${MAKE} -C .. compile

lint:
	@${MAKE} -C .. xref dialyzer

test:
	@${MAKE} -C .. test
