FROM Appbase

COPY api-static/ /var/www/Cont1

RUN cd /var/www/Cont1 && \
	ln -s $PWD/nginx/nginx.conf /etc/nginx/conf.d

RUN cd /var/www/Cont1 && \
	ln -s $PWD/nginx/uwsgi /etc/init.d/

# Disable daemon mode for nginx
RUN echo "daemon off;" >> /etc/nginx/nginx.conf

# Install supervisord
RUN cd /usr/local/bin && \
	pip install supervisor

# Drop in supervisor config
COPY supervisord.conf /usr/local/etc/supervisord.conf 

# Expose port 8092 and start supervisor
EXPOSE 8092
CMD ["/usr/local/bin/supervisord"]
