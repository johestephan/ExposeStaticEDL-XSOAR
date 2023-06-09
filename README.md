# ExposeStaticEDL (aka SCPtoEDL)
This integration fetches a static file via SCP from a remote server and exposes the file to a specified port (static EDL, file display, etc)

This integration will require the creation of a new docker container image

    /docker_image_create name=demisto/scptoedl:latest base="demisto/python3-deb:3.8.2.6981" dependencies=bottle,paramiko,scp,gunicorn

### What's working (Version v3):
* SSH to remote server and retrieve a file
* SSL via gunicorn
* Expose file via set port
* If "Long Running" is disabled or !SCPtoEDL-refetch is used, the remote file will be converted in to an line-by-line array, please use extend-context if needed
* Usage of SSL  
* the integration exposes /refresh, so a file can be updated (recommended usage:

        !http method=GET url=IP:PORT/refresh
        
### GetDiffs Script (v1)
GetDiffs can be used to compare two different lists, currently it expects to have two lists available in the context data
* newDAG
* currentDAG

and the script will identify which items to add or remove from the list.

        !GetDiffs

### Known Issues:
* https://github.com/johestephan/ExposeStaticEDL-XSOAR/issues

### Usage:
* Remote host -> IP of server
* Remote path -> path to file (ex. /tmp/)
* Remote file -> filename (ex. test.txt)
* Port -> Exposed port of edl
* SSH user 
* SSH Password
* Optional (v2)
    * Set SSL keys for HTTPS 
* Enable "Long Running Instance"

### Support Level:
* Community
* Process to get the integration into the Marketplace via Community contribution - pending


### Community Contributed Integration
#### Integration Author: Joerg Stephan (https://cybernotdienst.de)
No support or maintenance is provided by the author. Customers are encouraged to engage with the user community for questions and guidance at the [Cortex XSOAR Live Discussions](https://live.paloaltonetworks.com/t5/cortex-xsoar-discussions/bd-p/Cortex_XSOAR_Discussions).

---
[View Integration Documentation](https://xsoar.pan.dev/docs/reference/integrations/hello-world)
