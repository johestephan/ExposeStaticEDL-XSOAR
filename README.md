# ExposeStaticEDL
This integration fetches a static file via SCP from a remote server and exposes the file to a specified port (static EDL, file display, etc)

This integration will require the creation of a new docker container image

    /docker_image_create name=mypyexpose base="demisto/python3-deb:3.8.2.6981" dependencies=bottle,paramiko,scp

What's working (Version 0.1):
* SSH to remote server and retrieve a file
* Expose file via set port 

What's not working:
* Auto restart and fetch file on remote file change

Known Issues:
* https://github.com/johestephan/ExposeStaticEDL-XSOAR/issues

Usage:
* Remote host -> IP of server
* Remote path -> path to file (ex. /tmp/)
* Remote file -> filename (ex. test.txt)
* Port -> Exposed port of edl
* SSH user 
* SSH Password

Support Level:
* Community
* Process to get the integration into the Marketplace via Community contribution - pending


### Community Contributed Integration
#### Integration Author: Joerg Stephan (https://cybernotdienst.de)
No support or maintenance is provided by the author. Customers are encouraged to engage with the user community for questions and guidance at the [Cortex XSOAR Live Discussions](https://live.paloaltonetworks.com/t5/cortex-xsoar-discussions/bd-p/Cortex_XSOAR_Discussions).

---
[View Integration Documentation](https://xsoar.pan.dev/docs/reference/integrations/hello-world)
