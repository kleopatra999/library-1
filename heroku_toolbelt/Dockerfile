FROM dockbit/base:latest
MAINTAINER The Dockbit Team "team@dockbit.com"

# Install Heroku Toolbelt (Legacy) via RubyGems
WORKDIR /tmp
COPY components/heroku_toolbelt.sh .
RUN ./heroku_toolbelt.sh

# Cleanup & execution environment
USER root
RUN rm -f heroku_toolbelt.sh
COPY docker-entrypoint.sh /docker-entrypoint.sh
USER dockbit
WORKDIR /home/dockbit
ENTRYPOINT ["/docker-entrypoint.sh"]