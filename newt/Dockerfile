# https://developers.home-assistant.io/docs/add-ons/configuration#add-on-dockerfile
ARG BUILD_FROM
ARG NEWT_VERSION=latest

FROM fosrl/newt:${NEWT_VERSION} AS binary

FROM $BUILD_FROM

# Copy Newt binary
COPY --from=binary /usr/local/bin/newt /usr/local/bin/newt

# Execute during the build of the image
ARG TEMPIO_VERSION BUILD_ARCH
RUN \
    curl -sSLf -o /usr/bin/tempio \
    "https://github.com/home-assistant/tempio/releases/download/${TEMPIO_VERSION}/tempio_${BUILD_ARCH}"

# Copy root filesystem
COPY rootfs /
