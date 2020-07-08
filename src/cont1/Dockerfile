FROM python:2.7

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get -q update && \
	apt-get -y -q install \
	nginx \
	libjpeg-dev \
	zlibc \
	zip \
	supervisor

# Drop in application source
RUN mkdir -p /var/www/forklift
COPY api-static/ /var/www/forklift

# Disable daemon mode for nginx and remove default site page
RUN echo "daemon off;" >> /etc/nginx/nginx.conf
RUN rm /etc/nginx/sites-enabled/default

# Install python packages
RUN cd /var/www/forklift && \
	virtualenv venv && \
	. venv/bin/activate && \
	pip install uwsgi numpy geopy flask pillow boto3

# Drop in application nginx config
RUN cd /var/www/forklift && \
	ln -s $PWD/nginx/nginx.conf /etc/nginx/conf.d

# Drop in supervisor config
COPY supervisord.conf /etc/supervisor/conf.d/

# Expose port 8000 and start supervisor
EXPOSE 8000/tcp
CMD ["/usr/bin/supervisord"]
