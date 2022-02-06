# nginx-proxy

Automatic ssl-terminating reverse proxy.

This project contains three containers:
The nginx container works as the proxy.
The docker-gen container listens for new containers and manages the config file for nginx.
The acme-companion container generates and manages the ssl certificates for the hosts.

## Important step when deploying
The docker-gen container needs a template file called `nginx.tmpl` which can be found [here](https://github.com/nginx-proxy/nginx-proxy/blob/main/nginx.tmpl)
Place this file next to the docker-compose file when deploying locally.
Deploy the stack and upload the file to the named volume. Restart the docker-gen container afterwards.

