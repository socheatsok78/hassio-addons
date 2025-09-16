# https://developers.home-assistant.io/docs/add-ons/configuration#add-on-dockerfile
ARG BUILD_FROM
ARG NEWT_VERSION=1.4.4

FROM fosrl/newt:${NEWT_VERSION} AS binary

FROM $BUILD_FROM

# Execute during the build of the image
ARG TEMPIO_VERSION BUILD_ARCH
RUN \
    curl -sSLf -o /usr/bin/tempio \
    "https://github.com/home-assistant/tempio/releases/download/${TEMPIO_VERSION}/tempio_${BUILD_ARCH}"

# Copy Newt binary
COPY --from=binary /usr/local/bin/newt /usr/local/bin/newt

# Copy root filesystem
COPY rootfs /
