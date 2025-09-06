FROM alpine:3.22

# Update Alpine and install some basic tools
RUN apk update && apk add --no-cache \
    curl \
    alpine-sdk \
    make \
    libxml2-dev \
    json-c-dev \
    libc++ \
    libc++-dev \
    autoconf \
    llvm-libunwind-dev

# get freesasa source file
RUN curl -O https://freesasa.github.io/freesasa-2.1.2.zip

# decompress and set working directory
RUN unzip freesasa-2.1.2.zip
WORKDIR freesasa-2.1.2

# configure compile and install 
RUN ./configure
RUN make 
RUN make install

# reset the work directory
WORKDIR /

RUN rm -r freesasa-2.1.2 freesasa-2.1.2.zip
