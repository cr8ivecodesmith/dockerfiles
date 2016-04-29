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

#### Running as specific user

A default non-root user is created called `py3kit` which is assigned the default
UID for first users.

If you have a different UID, you must create a new image based on this with a
user that has the same UID.

See the `USER` section in:
https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/


#### Run a ipython shell

```
docker-compose run --rm ipython
```


#### Run an ipython notebook server

```
docker-compose run --rm --service-ports -v `pwd`:/notebooks -w /notebooks notebook
```

Then visit your browser at:

http://localhost:8888/


#### Start a Django project

```
docker run --rm -it -u py3kit -v `pwd`:/projects -w /projects py3kit:latest django-admin startproject helloapp
```

You can also use the same approach above to run other built-in packages in this
image.


[1]: https://docs.docker.com/engine/installation/
[2]: https://docs.docker.com/compose/install/
