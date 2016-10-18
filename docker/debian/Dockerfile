# Using debian base (247MB) for simple apk installs
FROM debian:latest

# Image for base ruby environment
MAINTAINER kyle-cook

RUN apt-get update && apt-get upgrade && apt-get install -y apt-utils

# ROOT Opperations
# Configure IP (based on 10.0.0.0/8 Gateway), DHCP, DNS, Domain, rsyslog

# Most nodes will be able to build anything
RUN apt-get install -y build-essential
RUN apt-get install -y kernel-package
RUN apt-get install -y kernel-common
# Be able to build for mobile architectures
#RUN apt-get install -y libc6-armel-cross libc6-dev-armel-cross
#RUN apt-get install -y binutils-arm-linux-gnueabi
#RUN apt-get install -y libncurses5-dev
# All nodes will be routing capable
RUN apt-get install -y iptables
# Be capable of building BPF and being a network sensor
RUN apt-get install -y libpcap-dev

# Download and install build tools, cross platform where applicable
RUN apt-get install -y automake
RUN apt-get install -y git
RUN apt-get install -y mercurial
RUN apt-get install -y subversion
RUN apt-get install -y cvs
RUN apt-get install -y curl
RUN apt-get install -y ruby
RUN apt-get install -y python
RUN apt-get install -y python3
RUN apt-get install -y default-jre
RUN apt-get install -y default-jdk
RUN apt-get install -y vim
RUN apt-get install -y emacs
# SSH is not required for most machines and should be stood up outside of this image stamping process due to the way certificates are generated
#RUN apt-get install -y ssh

# Be able to generate a random identity as a 'local user' (customer/attacker simulation)
RUN apt-get install -y rig

RUN apt-get install -y bind9

# Create groups based on execution space, storage location, and data types(tags)
# Example groups : [nids, hids, www, trace, pii, phi, pci, phr, key, src]
# Forbidden groups : [ssn] Here you can blacklist key words, legal, offensive, tips

# Create users for groups
# Reserved Users
RUN useradd -ms /bin/bash apache
RUN useradd -ms /bin/bash kc
RUN useradd -ms /bin/bash metasploit
# Generate 250,000 mock users with Package: rig each getting a 10mb home+logging storage limit

# Copy all the gems into the image [application/code]
#ADD ./gems ~/.ruby/gems
