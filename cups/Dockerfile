ARG BUILD_FROM
FROM $BUILD_FROM

COPY run.sh /
RUN chmod a+x /run.sh

# Set debug mode for CUPS
ENV CUPS_DEBUG_LOG=cups-debug.log
ENV CUPS_DEBUG_LEVEL=debug

EXPOSE 631


CMD [ "/run.sh" ]

LABEL \
    io.hass.name="CUPS Print Server" \
    io.hass.description="CUPS Print Server add-on for Home Assistant" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version=${BUILD_VERSION}
