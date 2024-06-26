# Self-hosted ghost server

Tech stack: Docker, Traefik, Ghost, MySQL

Author: [Robert Chang](https://github.com/RobertChang0722/)

## Description

1. Install docker on your server
2. Clone this repository
3. Rename the `.env-template` to `.env`

```bash
$ mv .env-template .env
```

4. Modify the `.env` file the MUST HAVE variables
5. Fill in your email in the traefik.yml file (line 23)
6. Change the permission of `acme.json` to 600
  
```bash
$ sudo chmod 600 ./acme.json
```

7. Create basic network & volume

```bash
$ docker network create traefik
$ docker network create backend
$ docker volume create ghostdata
$ docker volume create mysql
```

8. Run `docker compose up -d` to start the ghost server