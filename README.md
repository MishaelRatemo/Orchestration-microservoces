# Orchastartion

## Running the application

 For the appicaton to run run the forllowing commands

 ###  start up the build process
 `sudo docker-compose build`  in the folderf for which yaml file rests. 
 NB. uncomment the npm install redis

 ###  Run the services form .yml file using compose command
 `sudo docker-compose up` this successfully orchastrates te services

 ### List the containers associated with docker compose project
  ` docker-compose ps` Ths should be run in a seperate terminal

## Testing out the functionality
On another terminal:
`curl http://0.0.0.0:8080`

`curl http://0.0.0.0:8080/run`  runs a one-off commmand

`curl http://0.0.0.0:8080/scale` This sets a number of containers for a service

`curl http://0.0.0.0:8080/build` Builds or rebuilds services


## Cleaning up
Finally, we need to clean up after ourselves by stopping the web-server, otherwise we might run into some conflicts later in the module when we try to use/listen-to the port(s) that are currently being utilized by the services
in the directory containing the docker-compose file to stop the processes that we just initiated.
`sudo docker-compose rm`

Confirm whether any of the services that we initialized from the dockerfile above are running by listing them using:
`docker ps | grep service-name` in our case is either web or redis

