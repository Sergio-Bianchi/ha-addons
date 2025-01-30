ARG BUILD_FROM=ghcr.io/home-assistant/aarch64-base:3.18
FROM ${BUILD_FROM}

# Install CUPS only
RUN apk add --no-cache cups && \
    mkdir -p /var/run/cups/certs && \
    mkdir -p /var/log/cups && \
    mkdir -p /etc/cups && \
    chmod 0755 /var/run/cups/certs

# Copy root filesystem
COPY rootfs /

# Set debug mode for CUPS
ENV CUPS_DEBUG_LOG=cups-debug.log
ENV CUPS_DEBUG_LEVEL=debug

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
