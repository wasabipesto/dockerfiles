FROM alpine:3

RUN apk update
RUN apk --no-cache add curl

ENV ENDPOINT_URL=http://google.com
CMD while true; do curl $ENDPOINT_URL; sleep 30; done