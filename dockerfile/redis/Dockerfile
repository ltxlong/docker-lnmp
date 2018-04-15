FROM alpine:latest
MAINTAINER ltxlong

# Change Timezone
ARG TIME_ZONE=UTC
ENV TIME_ZONE ${TIME_ZONE}
RUN apk --update add redis && rm -rf /var/cache/apk/*
RUN ln -snf /usr/share/zoneinfo/$TIME_ZONE /etc/localtime && echo $TIME_ZONE > /etc/timezone

CMD [ "redis-server"]