FROM golang:1.3.3

RUN go get github.com/mitchellh/gox
RUN gox -build-toolchain

CMD go get -d ./... && gox
