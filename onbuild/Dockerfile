ARG BASE_IMAGE="alpine:latest"

FROM ${BASE_IMAGE}

LABEL description=${DESCRIPTION}
LABEL maintainer="Romain THERRAT <romain@pockost.com>"

ARG VCS_URL="https://github.com/pockost/docker-borgbackup"
ARG DESCRIPTION="Docker image for runnning borgbackup"
ONBUILD ARG IMAGE_NAME
ONBUILD ARG VCS_REF
ONBUILD ARG VERSION
ONBUILD ARG BUILD_DATE

ONBUILD RUN apk add --no-cache borgbackup=$VERSION

# Add image labels (https://microbadger.com/labels)
LABEL org.label-schema.schema-version="1.0" \
      org.label-schema.vendor="POCKOST" \
      org.label-schema.vcs-url=${VCS_URL} \
      org.label-schema.name="${IMAGE_NAME}" \
      org.label-schema.description="${DESCRIPTION}" \
      org.label-schema.url="https://www.pockost.com/" \
      org.label-schema.build-date="${BUILD_DATE}" \
      org.label-schema.vcs-ref=${VCS_REF}

ONBUILD LABEL org.label-schema.version="${VERSION}" \
      org.label-schema.build-date="${BUILD_DATE}" \
      org.label-schema.vcs-ref=${VCS_REF}

WORKDIR /src

EXPOSE 1313

#ENTRYPOINT ["/usr/local/sbin/borgbackup"]
#CMD ["serve", "--bind=0.0.0.0"]
