FROM alpine:3.22

# Update Alpine and install some basic tools
RUN apk update && apk add --no-cache \
    curl \
    git \
    alpine-sdk \
    make
 
# Clone the repository and set working directory
RUN git clone https://github.com/MDAnalysis/stride.git

# Change working directory to the cloned repo
WORKDIR stride/src

# buil stride from the source code 
RUN make

# move stride exe to the PATH directory
RUN mv stride /bin/

# Clean the repo that is no longer necessary
RUN rm -rf /stride

# reset the work directory
WORKDIR /
