FROM golang:1.16-bullseye

EXPOSE 8080

WORKDIR /usr/src/app

COPY . .

RUN go build && \
    useradd -m appuser

ENV REQUEST_ORIGIN=http://127.0.0.1:5000

USER appuser

CMD [ "./server" ]