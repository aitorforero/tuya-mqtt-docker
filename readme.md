![Create release with docker](https://github.com/aitorforero/tuya-mqtt-docker/workflows/Create%20release%20with%20docker/badge.svg)
# Docker image for tuya-mqtt
forked from https://github.com/mwinters-stuff/tuya-mqtt

See https://github.com/aitorforero/tuya-mqtt forked from https://github.com/TheAgentK/tuya-mqtt

Takes the above repository, and wraps it in a docker image, 

## Usage
### Simple

1. create a directory for the config files to go into, this is mounted into a volume /config (eg $(pwd)/config)
2. inital run to create the default config files
   > docker run -it --rm -v $(pwd)/config:/config ghcr.io/mwinters-stuff/tuya-mqtt-docker:latest
3. Stop the docker image with ctrl-c
4. Edit the config/config.json file to point to your mqtt server
5. Edit the config/devices.conf to add your devices.
6. Run again in background
   > docker-run -v $(pwd)/config:/config ghcr.io/mwinters-stuff/tuya-mqtt-docker:latest

### Docker-compose
Repeat steps 1 to 5 above, then use the following docker-compose entry
```lua
  tuya-mqtt:
    image: ghcr.io/mwinters-stuff/tuya-mqtt-docker:v3.0.0
    restart: "always"
    volumes:
      - "./config:/config"
```
Customise as required and start.



