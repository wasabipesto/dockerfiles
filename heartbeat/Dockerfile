FROM alpine:3
RUN apk --no-cache add curl

ENV ENDPOINT_URL=http://google.com
ENV TIMEOUT=30
CMD while true; do curl -sSf $ENDPOINT_URL; sleep $TIMEOUT; done
