FROM ubuntu:16.04

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        build-essential \
	ca-certificates \
	git

RUN cd $HOME && \
	git clone https://github.com/ph4r/tcptunnel.git && \
	cd tcptunnel && \
	./configure && \
	make && \
	make install

RUN yes | apt-get remove \
	build-essential \
	git && \
	yes | apt-get autoremove

ENTRYPOINT /root/tcptunnel/tcptunnel
