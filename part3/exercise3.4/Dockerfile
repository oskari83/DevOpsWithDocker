FROM golang:1.16

EXPOSE 8080

WORKDIR /usr/src/app

COPY . .

RUN go build

ENV REQUEST_ORIGIN=http://127.0.0.1:5000

RUN useradd -m appuser

USER appuser

CMD [ "./server" ]