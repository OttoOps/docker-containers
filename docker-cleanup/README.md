This image cleans up stopped Docker containers on a given server. It is particularly useful for environments running Docker containers on Apache Mesos, where the number of old containers can grow rather quickly. 

The docker-cleanup image containerizes a cron job. The frequency of the cron job can be set via the CMD parameter when the Docker container is started.

ex. docker run -d docker-cleanup 30

Valid frequency values are between 1 - 59 minutes.