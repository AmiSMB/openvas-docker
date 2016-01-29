OpenVAS image for Docker
==============

[![Circle CI](https://img.shields.io/circleci/project/amismb/openvas-docker.svg)](https://circleci.com/gh/amismb/openvas-docker)
[![Docker Pulls](https://img.shields.io/docker/pulls/amismb/openvas.svg)](https://hub.docker.com/r/amismb/openvas-docker/)
[![Docker Stars](https://img.shields.io/docker/stars/mikesplain/openvas.svg)](https://hub.docker.com/r/amismb/openvas-docker/)

A Docker container for OpenVAS 8 on the Ubuntu 14.04 image.  By default, the latest images includes the OpenVAS Base as well as the NVTs and Certs required to run OpenVAS.

Requirements
------------
Docker
Ports available: 443, 9390, 9391

Usage
-----

Simply run:

```
docker run -d -p 443:443 -p 9390:9390 -p 9391:9391 -p 9392:9392 --name openvas amismb/openvas-docker
```

This will grab the container from the docker registry and start it up.  Openvas startup can take some time (4-5 minutes while NVT's are scanned and databases rebuilt), so be patient.  Once you see a `gasd` process in the top command below, the web ui is good to go.  Goto `https://<machinename>`

```
Username: admin
Password: openvas
```

To check the status of the process, run:

```
docker top openvas
```

In the output, look for the process scanning cert data.  It contains a percentage.

To run bash inside the container run:

```
docker exec -it openvas bash
```
# Open PR


Contributing
------------

I'm always happy to accept [pull requests](https://github.com/mikesplain/openvas-docker/pulls) or [issues](https://github.com/amismb/openvas-docker/issues).

Thanks
------
Thanks to hackertarget for the great tutorial: http://hackertarget.com/install-openvas-7-ubuntu/
Thanks to Serge Katzmann for contributing with some great work on OpenVAS 8: https://github.com/sergekatzmann/openvas8-complete
Thanks to Mike Splain for the work on OpenVAS which this project is forked from:
https://github.com/mikesplain/openvas-docker
