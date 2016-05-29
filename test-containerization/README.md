# Robot Test Containerization

How to containerize RobotFramework [tests](https://bitbucket.org/robotframework/webdemo) in 5 minutes.

**Requirements:**  
* [docker-toolbox](https://www.docker.com/products/docker-toolbox)
* [Demoapp](../demoapp-containerization/README.md) must be running


**Docker Machine Commands:**  
* Creating a machine (called slave): `docker-machine create -d virtualbox slave`
* Deleting the machine: `docker-machine rm -f slave`

**Launch Commands:**  
* Build tests into Docker image: `docker build -t testimage .`
* Run tests: `docker run --rm -v $(pwd)/test-output:/robo-tests/output:rw -v $(pwd)/robo-tests:/robo-tests/tests:ro --name testcontainer -it testimage -v SERVER:"$(docker-machine ip slave):7272" -v HEADLESS:True -v RESOURCE:xvfb --outputdir /robo-tests/output /robo-tests/tests`

**Cleanup Commands:**  
* Remove the container: `docker rm testcontainer`
* Remove the image: `docker rmi testimage`
