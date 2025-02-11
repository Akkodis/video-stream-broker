# 5GMETA MEC Platform Videao Broker (WebRTC Proxy)

## The Video Broker

- **WebRTC Proxy**: a module of the 5GMETA MEC platform to receive the Video Stream in WebRTC format turning it into a UDP stream and AMQP messages (1 per frame) ready to be processed by Pipelines running at the 5GMETA MEC infrastructure. The instructions for that can be found in [`deploy`](../deploy) folder while the code in [`src`](webrtc_proxy) folder


## A client used for testing
- **VideoSensor**: an example to push a Video Stream to the 5GMETA MEC infrastructure. The instructions for that can be found in [`deploy`](../deploy) folder while the code in [`src`](video_sensor) folder
