# syntax=docker/dockerfile-upstream:master
ARG UPSTREAM_VERSION=2.1.2 #changed to 2.1.2
FROM aztecprotocol/aztec:${UPSTREAM_VERSION#v}

ARG NETWORK
ARG L1_CHAIN_ID
ARG DATA_DIRECTORY

ENV NETWORK=${NETWORK} \
    L1_CHAIN_ID=${L1_CHAIN_ID} \
    DATA_DIRECTORY=${DATA_DIRECTORY}

COPY entrypoint.sh /usr/local/bin/entrypoint.sh
RUN chmod +x /usr/local/bin/entrypoint.sh
RUN apt-get update && apt-get install -y lz4 wget
ENTRYPOINT ["/usr/local/bin/entrypoint.sh"]
