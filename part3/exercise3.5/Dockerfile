FROM golang:1.16-alpine3.14

EXPOSE 8080

WORKDIR /usr/src/app

COPY . .

RUN go build && \
    adduser -D appuser

ENV REQUEST_ORIGIN=http://127.0.0.1:5000

USER appuser

CMD [ "./server" ]