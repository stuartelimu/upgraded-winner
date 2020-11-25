# upgraded-winner
Django + Docker with Postgresql

## Setup & Installation
- create Dockerfile
- create requirements.txt file
- create docker-compose.yml file
- run 
```
sudo docker-compose run web django-admin startproject <project_name> .
```

- change ownership of new files, run 
```
sudo chown -R $USER:$USER .
```

### Adding postgres
- install  `psycopg` adopter
```
docker-compose exec web pip install psycopg2-binary>=2.8
```
- update requirements.txt 
```
docker-compose exec web pip freeze > requirements.txt
```
- add postres [settings]()
- stop the container
```
docker-compose down
```
- start the container, `--build` flag rebuilds the container with updated packages 
```
docker-compose up -d --build
```
- `-d` flag runs docker in the background

## commands
- [docker-compose exec](https://docs.docker.com/compose/reference/exec/)
- [docker-compose run](https://docs.docker.com/compose/reference/run/)
- [docker-compose up](https://docs.docker.com/compose/reference/up/)
- [docker-compose logs](https://docs.docker.com/compose/reference/logs/)
- [docker-compose ps](https://docs.docker.com/compose/reference/ps/)

## credits
- [Quickstart: Compose and Django](https://docs.docker.com/compose/django/)
- [Django for Professionals](https://djangoforprofessionals.com/)