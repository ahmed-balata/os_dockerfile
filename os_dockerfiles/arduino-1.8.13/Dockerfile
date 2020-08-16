FROM i386/ubuntu:18.04

MAINTAINER Ahemd Balata

# setup
RUN apt-get -qq update && apt-get install -y \
            make \
            python-pip \
	    python-serial \
            automake \
            sudo &&\
	    sudo apt-get install -y avr-libc gcc-avr


