FROM Appbase

COPY api-static/ /var/www/Cont1

RUN cd /var/www/Cont1 && \
	ln -s $PWD/nginx/nginx.conf /etc/nginx/conf.d

# Disable daemon mode for nginx
RUN echo "daemon off;" >> /etc/nginx/nginx.conf

EXPOSE 8000

# Set working directory
WORKDIR /var/www/Cont1/

# Set the default command to execute when creating a new container
CMD service nginx start
