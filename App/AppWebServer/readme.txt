AppWebServer handles the HTTP communication and displays the frontend. Contains only all of the HTML files to run the website.


This directory contains the Dockerfile to create the App Web Server container
It depends on the app:base container

The app:webserver container is responsible for handling and servicing all request from the web pages.

It forwards all actions to their respective micro service containers.  

The following microservices containers are available:

app:info -> handles all /info and /cookie HTTP requests
app:processor -> handles all /images* HTTP requests


INSTRUCTIONS:
1. CD AppWebServer
2. docker build -t app:webserver .
3. docker run --name App -d -p 8000:8000 App:webserver
