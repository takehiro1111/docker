FROM fluent/fluentd:v1.17-1

# Use root account to use apk
USER root

# below RUN includes plugin as examples elasticsearch is not required
# you may customize including plugins as you wish
RUN apk add --no-cache --update --virtual .build-deps \
        sudo build-base ruby-dev \
  && sudo gem install fluent-plugin-elasticsearch \
  && sudo gem sources --clear-all \
  && apk del .build-deps \
  && rm -rf /tmp/* /var/tmp/* /usr/lib/ruby/gems/*/cache/*.gem

COPY conf.d/* /fluentd/etc/
EXPOSE 24224
# COPY entrypoint.sh /bin/

USER fluent


# pluginなどの部分は仕様を決めてインストールする必要がある。
