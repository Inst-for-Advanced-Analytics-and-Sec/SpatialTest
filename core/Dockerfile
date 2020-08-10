# Start from the official Ubuntu 17.10 image
# Base image Ubuntu !8:04
FROM ubuntu:18.04

## Set environment variables
ENV LANG=C.UTF-8 LC_ALL=C.UTF-8

# Install system packages and utilities
RUN apt-get update
RUN apt-get install -y wget \
	bzip2 \
	ca-certificates \
	build-essential \
	curl \
	git-core \
	pkg-config \
	python3-dev \
	python3-pip \
	python3-setuptools \
	python3-virtualenv \
	unzip \
	software-properties-common \
	llvm

#Install Gdal libraries
RUN apt install -y gdal-bin python-gdal python3-gdal

## Upgrade pip(package manger)
RUN pip3 install --upgrade pip
# write your code
ENV PYTHONUNBUFFERED 1

# create a working directory
WORKDIR /app

ADD . /app

# copy the project requirements file into the working directory
COPY ./requirements.txt /app/requirements.txt

#install all the required packages
RUN pip3 install -r requirements.txt

#copy the source code
COPY . /app

#Expose the port
EXPOSE 8000
