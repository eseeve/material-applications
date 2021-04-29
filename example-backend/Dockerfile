FROM golang:1.16

EXPOSE 8080

WORKDIR /usr/src/app

RUN useradd -m appuser
RUN chown appuser ./

USER appuser

COPY . .

ENV REQUEST_ORIGIN=http://localhost/

RUN go build

CMD "./server"