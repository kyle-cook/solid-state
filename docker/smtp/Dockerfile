# Using debian base (247MB) for simple apk installs
FROM debian:latest

# Image for base ruby environment
MAINTAINER kyle-cook

RUN apt-get update && apt-get upgrade && apt-get install -y apt-utils

# ROOT Opperations
# Configure IP (based on 10.0.0.0/8 Gateway), DHCP, DNS, Domain, rsyslog, SMTP

# Most nodes will be able to build anything
RUN apt-get install -y build-essential
RUN apt-get install -y kernel-package
RUN apt-get install -y kernel-common
RUN apt-get install -y sendmail
