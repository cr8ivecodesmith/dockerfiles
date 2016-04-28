Python3 Development Toolkit
===========================

A bleeding edge development environment for Python3.

Most suitable for experimentations and writing your own notebooks and teaching
python.

See other packages installed in the `requirements.txt` file.


## Requirements

Latest [Docker][1] and [Docker Compose][2] for your OS.


Docker images of the ff:

- python:3.5
- cr8ivecodesmith/py3kit:latest


## Usages

**Run a ipython shell:**

```
docker-compose run --rm ipython
```

**Run an ipython notebook server:**

```
docker-compose run --rm --service-ports notebook
```

Then visit your browser at:

http://localhost:8888/


**Start a Django project**

```
docker run --rm -it py3kit:latest django-admin startproject
```

You can also use the same approach above to run other built-in packages in this
image.


[1]: https://docs.docker.com/engine/installation/
[2]: https://docs.docker.com/compose/install/
