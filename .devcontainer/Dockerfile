FROM mcr.microsoft.com/devcontainers/base:jammy

RUN apt update \
    && apt install --no-install-recommends -y rsyslog systemd systemd-cron dbus \
    # Fix a bug with common-debian script
    && rm -f /usr/local/bin/systemctl \
    #  Clean up
    && apt clean && rm -rf /var/lib/apt/lists/*

CMD ["/lib/systemd/systemd", "--system", "--unit=basic.target"]
