# container-nomad [![Build Status](https://cloud.drone.io/api/badges/yellowmegaman/container-nomad/status.svg)](https://cloud.drone.io/yellowmegaman/container-nomad)

Docker image with Hashicorp Nomad + Hashicorp consul-template.
Can be used for templated remote nomad deploys.

Example usage:
```
docker run -it yellowmegaman/container-nomad:latest bash
$ consul-template -consul-addr=$TARGET:8500 -once -template job.teplate:job.rendered
$ nomad plan -address=http://$TARGET:4646 job.rendered
$ nomad run -address=http://$TARGET:4646 job.rendered
$ <assessment script> 
```
