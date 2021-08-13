# MetaDomainHotSpot


## Software Requirements

The MetaDomain HotSpot software makes use of jupyter notebooks and requires been tested in a Linux-based OS (tested on Ubuntu 18.04), but as it is fully containerized in docker it should in theory be possible to run it on any other OS.
Please ensure you have the following software installed on your machine:

	docker

You can get docker [here](https://www.docker.com/get-docker)

## Running the notebook

To start the jupyter notebook:
```
docker run -d -p 8888:8888 -v $(pwd):/home/jovyan/work --name MDHS_notebook jupyter/datascience-notebook
docker exec -it MDHS_notebook bash -c 'jupyter notebook list' | grep http | cut -f1 -d ' ' | awk '{sub(/8888/, "8888")}1' | xargs xdg-open
```

To shut the jupyter notebook down:

```
docker stop MDHS_notebook
```

To remove the jupyter notebook docker container:
```
docker rm MDHS_notebook
```
