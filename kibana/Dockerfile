FROM kibana:latest

RUN chmod +x docker-entrypoint.sh

RUN apt-get update && apt-get install -y netcat

COPY config/kibana.yml /opt/kibana/config/kibana.yml
COPY entrypoint.sh /tmp/entrypoint.sh
RUN chmod +x /tmp/entrypoint.sh

CMD ["/tmp/entrypoint.sh"]
