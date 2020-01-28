# diskover-spark
Example notebook that pulls data from Diskover crawl into Spark for analysis.

---
# Requirements and environment setup
* Docker
## Standing up Jupyter + Spark environment
### I'm using the jupyter-all-spark Docker image to spin up both Jupyter and Spark. I'm using volume re-direction in Docker to allow for Notebook persistence outside of the Docker container.
```bash
docker run \
-d \
--restart=always \
--name jupyter-all-spark \
-p 8888:8888 -v /home/jasdav02/Jupyter:/home/jovyan/work \
jupyter/all-spark-notebook
```
### Once running, you'll need to fetch the authentication token
```bash
docker exec \
-it jupyter-all-spark \
jupyter notebook list
```
```
Currently running servers:
http://0.0.0.0:8888/?token=5a3cdff4f94f2b333774a49b763acc1b27e7bdeae1d4dc43 :: /home/jovyan
```
### With token in hand, point your browser to `http://localhost:8888`
