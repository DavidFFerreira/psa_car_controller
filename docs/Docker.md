# Docker installation

A containerised version of the psa_car_controller.
- Docker Hub: https://hub.docker.com/r/DavidFFerreira/psa_car_controller

### Overview
Once the container is running, the configuration of the psa_car_controller app is near-identical classic Linux/Windows installtion.

### Installation
Create the container, detached, exposing port 5001, and mapping config folder on your host to /config inside the container:

#### With docker-compose
```
docker-compose up -d
```
#### With Docker:
```
docker run -d -ti --name psa_car_controller1 \
  --publish 5001:5001 \
  -v /host_path/config:/config \
  --restart unless-stopped \
  flobz/psa_car_controller
```
Go to http://127.0.0.1:5001 and follow instruction

### Environment variable:
You can modify some parameter with docker environment variable:

|variable         | description                     |
|-----------------|---------------------------------|
|PSACC_CONFIG_DIR | overide configuration directory |
|PSACC_PORT       | change port                     |
|PSACC_OPTIONS    | add cli argurment               |



