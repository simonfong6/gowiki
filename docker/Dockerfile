FROM ubuntu:bionic-20210512

RUN apt update -y && \
    apt install -y \
        wget

# Install Go.
# https://golang.org/doc/install
RUN wget https://golang.org/dl/go1.16.4.linux-amd64.tar.gz && \
    rm -rf /usr/local/go && \
    tar -C /usr/local -xzf go1.16.4.linux-amd64.tar.gz && \
    rm go1.16.4.linux-amd64.tar.gz

ENV PATH=$PATH:/usr/local/go/bin

WORKDIR /app

COPY . /app

RUN go build wiki.go

CMD ["/app/wiki"]
