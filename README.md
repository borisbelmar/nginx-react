# Nginx React Ready

This image replaces the Nginx `default.conf` file in order to correctly serve a SPA with routing. Is based on Romain Cauquil's publication ["How to use react-router with Nginx and Docker"](https://romaincauquil.fr/blog/2017/how-to-use-react-router-nginx-docker/).

### Usage

Just put your built project on `/usr/share/nginx/html`

This is an example using `docker-compose` and `nginx-proxy`.

```yaml
react-app:
  image: borisbelmar/nginx-react:latest
  expose:
    - "80"
  volumes:
    - /home/user/react-app/build:/usr/share/nginx/html:ro
  environment:
    - VIRTUAL_HOST=my-domain.com
    - LETSENCRYPT_HOST=my-domain.com
    - LETSENCRYPT_EMAIL=user@my-domain.com
```