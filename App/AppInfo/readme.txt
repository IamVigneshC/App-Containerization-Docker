This directory contains the Dockerfile to create the App Info container

It depends on the app:base container

The app:processor container is responsible for handling and servicing all request from the web pages related to the following urls:
/info
/cookie

All html files are not part of this distribution.

INSTRUCTIONS:
1. CD AppInfo
2. docker build -t app:info .
3. docker run --name info -d -p 8092:8092 app:info
