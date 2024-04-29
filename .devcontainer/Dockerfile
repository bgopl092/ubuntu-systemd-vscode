FROM ubuntu:23.04

RUN apt update \
    && apt install --no-install-recommends -y rsyslog systemd systemd-cron dbus sudo wget curl nano software-properties-common language-pack-vi language-pack-vi-base locales locales-all \
    # Fix a bug with common-debian script
    && rm -f /usr/local/bin/systemctl \
    #  Clean up
    && apt clean && rm -rf /var/lib/apt/lists/* 
RUN locale-gen "vi_VN.UTF-8"
ENV LANG=vi_VN.UTF-8 \
    LANGUAGE=vi_VN:vi \
    LC_ALL=vi_VN.UTF-8

CMD ["/lib/systemd/systemd", "--system", "--unit=basic.target"]
