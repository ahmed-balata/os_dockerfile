FROM ubuntu:18.04

#git clone https://github.com/zephyrproject-rtos/zephyr
#https://docs.zephyrproject.org/latest/getting_started/index.html

#setup
RUN apt-get -y update && \
	apt-get -y upgrade && \
	apt-get install -y \
	sudo \
	python3-pip \
	gnupg2 &&\
	sudo apt-get -y install software-properties-common &&\
	pip3 install --user -U west

ENV PATH="/root/.local/bin:${PATH}"

#install dependencies
RUN sudo DEBIAN_FRONTEND=noninteractive apt -yq install --no-install-recommends git cmake ninja-build gperf \
  	ccache dfu-util device-tree-compiler wget \
	python3-dev python3-pip python3-setuptools python3-tk python3-wheel xz-utils file \
	make gcc gcc-multilib g++-multilib libsdl2-dev
	
#add the Kitware third-party apt repository to get an updated version of cmake.
RUN wget -O - https://apt.kitware.com/keys/kitware-archive-latest.asc 2>/dev/null | sudo apt-key add - &&\
	sudo apt-add-repository 'deb https://apt.kitware.com/ubuntu/ bionic main' &&\
	sudo apt update &&\
	sudo apt -y install cmake

RUN echo 'export PATH=/root/.local/bin:"$PATH"' >> ~/.bashrc
#RUN /bin/bash -c "source ~/.bashrc &&\
#	 /root/.local/bin/west init /home/ &&\
#	 cd /home/ &&\
#	 /root/.local/bin/west update &&\
#	 /root/.local/bin/west zephyr-export &&\
#	 pip3 install --user -r /home/zephyr/scripts/requirements.txt"

RUN west init /home/ &&\
	 cd /home/ &&\
	 west update &&\
	 west zephyr-export &&\
	 pip3 install --user -r /home/zephyr/scripts/requirements.txt


#Install a Toolchain
#A toolchain provides a compiler, assembler, linker, and other programs required to build Zephyr applications.
RUN cd ~ && wget https://github.com/zephyrproject-rtos/sdk-ng/releases/download/v0.11.3/zephyr-sdk-0.11.3-setup.run &&\
	chmod +x zephyr-sdk-0.11.3-setup.run &&\
	./zephyr-sdk-0.11.3-setup.run -- -d ~/zephyr-sdk-0.11.3



#ENV PATH="/root/.local/bin:${PATH}"
#COPY myscript1.sh /myscript1.sh
#ENTRYPOINT ["/myscript1.sh"]
#CMD ["/myscript1.sh"]
