# Overview

This docker image is designed to allow you to share you screen with your colleages on a *trusted network*, without requiring them to set up or configure a VNC client themselves.

This has not been tested for suitability on untrusted networks like the internet.

First you will need a vnc server on a the screen you want to share.

Simply start the container, assigning a port as necessary, like so:

    docker run -p 44444:6080 -it zenlambda/novnc_sharing

Here we map the default 6080 port to 44444.

When the server is running give the following URL to your colleage, 
substituting the variables as appropriate.


    http://$DOCKER_HOST:$MAPPED_PORT/vnc_auto.html?host=vnchost&port=5900

The meaning of the variables is as follows:

* `DOCKER_HOST` is the hostname of the machine hosting the docker container
* `MAPPED_PORT` the port mapped to the default 6080 port, in the previous example this would have been 44444.
