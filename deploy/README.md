# Deployment

This section overviews the way to deploy the containers for the following modules:
- **WebRTC Proxy** to receive the Video Stream in WebRTC format.
- **Video Sensor** to push a Video Stream to the 5GMETA MEC infrastructure.

- ***Prerequisites*** : 
    - docker

_For the convenience different **docker-compose.yaml** files are provided for the included systems. 
When using them, be sure you use the credentials and IP configuration that you want to use._

## WebRTC Proxy

* Navigate to [`src/webrtc_proxy`](../src/webrtc_proxy) folder, a Dockerfile contains all the information related to the container.
    - modify the `<path>` according to your environment:

* Move out of the webrtc_proxy directory (`<path>/src`)
    
    - ``` $ cd <path>/src ```
    - ``` $ docker build -t 5gmeta/webrtc_proxy webrtc_proxy/. ```
    - ``` $ docker run  --net=host --env AMQP_USER="<user>" --env AMQP_PASS="<password>" --env AMQP_IP="<AAA.BBB.CCC.DDD>" --env AMQP_PORT="<port>" 5gmeta/webrtc_proxy ```

 _Remember to configure the `<user`>, `<password`>, `<AAA.BBB.CCC.DDD`> and `<port`> to your local environment_

* ***NB: **AMQP_IP** and **AMQP_PORT** vars are only **required** for a **local test**. The actual parameters are retrieved from the Discovery at the 5GMETA Cloud @ EKS***


## Video Sensor

* Navigate to [`src/video_sensor`](../src/video_sensor) folder, a Dockerfile contains all the information related to the container.
    - modify the `<path>` according to your environment:


* Move out of the video_sensor directory (`<path>/src`)
    - Note that you need to change (latitude, longitude) in [`src/video_sensor/video_sensor.py`](../src/video_sensor/video_sensor.py) to match with your Device GPS position

    - ``` $ cd <path>/src ```
	- ``` $ docker build -t 5gmeta/video_sensor video_sensor/.```

***To see how to execute it go to the [`examples`](../examples/) folder***
