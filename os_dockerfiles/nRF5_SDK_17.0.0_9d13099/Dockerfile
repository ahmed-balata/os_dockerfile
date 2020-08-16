FROM ubuntu:xenial

MAINTAINER Ahmed Balata

# Setup
RUN apt-get update && apt-get install -y \
            wget \
            lib32ncurses5 \
            make \
            python-pip \
	    python-serial \
            automake \
            sudo


#install arm-gcc
#RUN sudo apt-get update -y && \
#	sudo apt-get install -y gcc-arm-none-eabi
RUN wget https://developer.arm.com/-/media/Files/downloads/gnu-rm/7-2018q2/gcc-arm-none-eabi-7-2018-q2-update-linux.tar.bz2 && \
	tar -xf gcc-arm-none-eabi-7-2018-q2-update-linux.tar.bz2 -C /usr/local














#WORKDIR is the mounted operating system directory
#WORKDIR /nRF5_SDK_17.0.0_9d13099
#ENTRYPOINT ["/nRF5_SDK_17.0.0_9d13099/.make_script.sh"]

#Download and install nRF Command Line Tools
#RUN wget https://www.nordicsemi.com/-/media/Software-and-other-downloads/Desktop-software/nRF-command-line-tools/sw/Versions-10-x-x/10-9-0/nRFCommandLineTools1090Linuxamd64tar.gz && \
#	tar -xvzf nRFCommandLineTools1090Linuxamd64tar.gz && \
#	dpkg -R --install *.deb




