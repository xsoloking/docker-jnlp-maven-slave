# Jenkins JNLP slave Docker image with Maven

[`qautomatron/docker-jnlp-maven-slave`](https://hub.docker.com/r/qautomatron/docker-jnlp-maven-slave/)

A [Jenkins](https://jenkins-ci.org) slave using JNLP to establish connection.

## Configuration specifics

By default, JnlpProtocol3 is disabled due to the known stability and scalability issues.
You can enable this protocol on your own risk using the
<code>JNLP_PROTOCOL_OPTS=-Dorg.jenkinsci.remoting.engine.JnlpProtocol3.disabled=false</code> property.

## Running

To run a Docker container

    docker run qautomatron/docker-jnlp-maven-slave -url http://jenkins-server:port <secret> <slave name>

optional environment variables:

* `JENKINS_URL`: url for the Jenkins server, can be used as a replacement to `-url` option, or to set alternate jenkins URL
* `JENKINS_TUNNEL`: (`HOST:PORT`) connect to this slave host and port instead of Jenkins server, assuming this one do route TCP traffic to Jenkins master. Useful when when Jenkins runs behind a load balancer, reverse proxy, etc.
