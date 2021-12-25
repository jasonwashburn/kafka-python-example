# kafka-python-example

A docker-compose stack for experimenting with Kafka in python.

## Basic Usage:

1. clone repo
2. cd into folder
3. run `docker compose build`
4. run `docker compose up`
5. click on (or paste into your browser) the link provided in the jupyter lab log output from the terminal window to
   access **Jupyter Lab** on [http://localhost:8888/](http://localhost:8888/)
6. **Note: you'll need the link with the token**. Another way to get the token if you dont want to scroll through the
   log output is to execute `docker logs jupyterlab 2>&1 | grep -A 2 "one of these URLs:"` in another terminal window.

## Development Tips:

### Jupyter Notebooks

- Jupyter notebooks are stored in the notebooks/ directory and mounted as a local volume so that your notebooks will
  persist between `docker compose up` and `docker compose down` cycles. Any changes you make to the notebooks will
  **not** be deleted between docker compose up and down cycles

### Kafka / Zookeeper

- The Kafka / Zookeeper data is stored persistently in a docker volume created by compose. If you want to scrap the
  existing message store run `docker compose down -v` which will bring down the containers and delete the
  volume so that you can start fresh. Note: this will **not** delete your notebooks folder.

## Examples:

Start with `00-kafka-producer.ipynb`
