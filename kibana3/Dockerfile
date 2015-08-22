FROM nginx

# Add the kibana user 
RUN useradd  -m -d /opt/kibana kibana

# Set the Kibana Version:
ENV KIBANA_VERSION 3.1.2

# Fetch Kibana
ADD https://download.elasticsearch.org/kibana/kibana/kibana-${KIBANA_VERSION}.tar.gz /tmp/kibana.tar.gz
RUN tar zxf /tmp/kibana.tar.gz && mv kibana-${KIBANA_VERSION}/* /opt/kibana

# Apply kiban and nginx configuration
ADD config/config.js /opt/kibana/config.js
ADD config/nginx.conf /etc/nginx/nginx.conf

# Change the Kibana installation files owner to elasticsearch:
RUN chown -R kibana:kibana /opt/kibana

WORKDIR /opt/kibana

# Define default command.
CMD ["nginx", "-g", "daemon off;"]