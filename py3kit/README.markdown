Python Development Toolkit
==========================

A bleeding edge development environment for Python.

Most suitable for experimentations, writing your own notebooks, and teaching
and learning python.


## Requirements

Latest [Docker][1] and [Docker Compose][2] for your OS.


## Included Python packages

- [python:latest][3]
- [python:2.7][4]


## Available Tags

- cr8ivecodesmith/pykit:latest
- cr8ivecodesmith/pykit:2.7


## Usages

You may have to get a copy of the Docker compose file fromt the Github repo
to run the compose commands below.


#### Run as a specific user

```
docker run --rm -it --user "$(id -u):$(id -g)" cr8ivecodesmith/pykit <command>
```

See the `USER` section in:
https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/


#### Run an ipython shell

```
docker-compose run --rm ipython
```


#### Run an ipython notebook server

```
docker-compose run -u "$(id -u):$(id -g)" --rm --service-ports notebook
```

Then visit your browser at:

http://localhost:8888/


#### Start a Django project

On Python 3:

```
docker run --rm -it --user "$(id -u):$(id -g)" -v `pwd`:/usr/src/app -w /usr/src/app cr8ivecodesmith/pykit:latest django-admin.py startproject helloworldapp
```

On Python 2.7:

```
docker run --rm -it --user "$(id -u):$(id -g)" -v `pwd`:/usr/src/app -w /usr/src/app cr8ivecodesmith/pykit:2.7 django-admin.py startproject helloworldapp
```

You can also use the same approach above to run other built-in packages in this
image.


[1]: https://docs.docker.com/engine/installation/
[2]: https://docs.docker.com/compose/install/
[3]: https://github.com/cr8ivecodesmith/dockerfiles/blob/master/py3kit/requirements.txt
[4]: https://github.com/cr8ivecodesmith/dockerfiles/blob/master/py2kit/requirements.txt
