# Using ubuntu base
FROM debian:latest

# Image for base ruby environment
MAINTAINER kyle-cook

RUN apt-get install -y ruby
RUN gem install -y sinatra

# Give ourselves a non-root user
USER ruby

# Copy all the gems into the image
#ADD ./gems ~/.ruby/gems
