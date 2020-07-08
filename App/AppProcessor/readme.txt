This directory contains the Dockerfile to create the App Image Processor container

It depends on the app:base container

The app:processor container is responsible for handling and servicing all request from the web pages related to images.

All html files are not part of this distribution.

INSTRUCTIONS:
1. CD AppProcessor
2. docker build -t app:processor .
3. docker run --name processor -d -p 8082:8082 app:processor
