FROM ubuntu:20.04
RUN apt-get update \
    && apt-get install curl unzip ca-certificates -y \
    && curl https://omniedge.io/install/omniedge-install.sh | bash

COPY entrypoint /usr/local/bin/entrypoint
RUN chmod +x /usr/local/bin/entrypoint

ENTRYPOINT ["/bin/bash"]