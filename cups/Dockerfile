ARG BUILD_FROM=ghcr.io/home-assistant/aarch64-base:3.18
FROM ${BUILD_FROM}

# Install CUPS and required packages
RUN apk add --no-cache \
    cups \
    cups-filters \
    cups-pdf \
    cups-client \
    hplip

# Copy root filesystem
COPY rootfs /

EXPOSE 631

# Build arguments
ARG BUILD_ARCH
ARG BUILD_DATE
ARG BUILD_REF
ARG BUILD_VERSION

# Labels
LABEL \
    io.hass.name="CUPS Print Server" \
    io.hass.description="CUPS Print Server add-on for Home Assistant" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version=${BUILD_VERSION}
