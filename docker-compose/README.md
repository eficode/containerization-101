# Docker Compose Demo

How to run [JIRA 7](https://www.atlassian.com/software/jira) in 5 minutes with docker compose.

**Requirements:**
* For docker compose: [docker-toolbox](https://www.docker.com/products/docker-toolbox)

**Docker Machine Commands:**
Creating a machine (called jira):  
* Create a machine: `docker-machine create -d virtualbox --virtualbox-memory 4096 jira`
* Activate the machine: `eval $(docker-machine env jira)`  
* Deleting the machine: `docker-machine rm -f jira`

**Docker Compose Commands:**
* Build and Run: `docker-compose up -d`
* See logs: `docker-compose logs`

**Accessing the application:**  
When using docker-machine:  
* Get the ip: `docker-machine ip jira`  
* Access with browser: `http://<machine ip>`  
When not using docker machine:  
* Access with browser: `http://localhost`


**Cleanup Commands:**
* Shut down: `docker-compose down`
