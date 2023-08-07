### titanic-ml-api
- https://tatiatic-ml-api.fly.dev/docs

## ENV
- python 3.9

- pyenv
```
$ pyenv install --list
$ pyenv install 3.9.16
$ pyenv global 3.9.16
$ pyenv versions
$ pyenv versions
  system
  3.7.16
* 3.9.16 (set by /home/tom/.pyenv/version)
```

- pipenv
```
$ pip install pipenv
$ pipenv --python 3.9.16
$ pipenv shell
```

## DEV
```
$ pipenv shell
$ pipenv install fastapi
$ pipenv install "uvicorn[standard]"
```

## RUN
- uvicorn app.main:app --reload

## DEPLOY
- docker
```
# Generate a requirements.txt from Pipfile.lock.
$ pipenv requirements > requirements.txt

$ docker build -t tatiatic-ml-api:0.1.0 .
$ docker images tatiatic-ml-api
REPOSITORY        TAG       IMAGE ID       CREATED          SIZE
tatiatic-ml-api   0.1.0     9c4500f3f26a   28 seconds ago   1.05GB

$ docker run -d --name tatiatic-ml-api-010 -p 5010:8080 tatiatic-ml-api:0.1.0
$ docker ps
CONTAINER ID   IMAGE                   COMMAND                  CREATED          STATUS          PORTS                    NAMES
e63bf91b996f   tatiatic-ml-api:0.1.0   "uvicorn app.main:ap…"   26 seconds ago   Up 25 seconds   0.0.0.0:5010->8080/tcp   tatiatic-ml-api-010
```

## REF
- https://fastapi.tiangolo.com/ko/
- https://fastapi.tiangolo.com/deployment/docker/#dockerfile