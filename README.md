# Docker Resque Web UI

![Docker Pulls](https://img.shields.io/docker/pulls/appwrite/resque-web.svg)
[![Discord](https://img.shields.io/discord/564160730845151244)](https://discord.gg/GSeTUeA)
[![Travis CI](https://badgen.net/travis/appwrite/docker-resque-ui?label=build)](https://travis-ci.org/appwrite/docker-resque-ui)

User interface container for the Redis [Resque Web UI](https://github.com/resque/resque-web) project. This container include default configuration to allow HTTP basic auth. Not recommended for production environments not running behind a network firewall.

## Usage

docker-compose.yml
```yml
resque:
  image: appwrite/resque-web:1.1.0
  links:
    - redis:redisserver
  ports:
    - "5678:5678"
  environment:
    - RESQUE_WEB_HOST=redisserver # (OPTIONAL - Use only if different than the default 127.0.0.1)
    - RESQUE_WEB_PORT=6379  # (OPTIONAL - Use only if different the default 6379)
    - RESQUE_WEB_HTTP_BASIC_AUTH_USER=user # (OPTIONAL - if not set no password used)
    - RESQUE_WEB_HTTP_BASIC_AUTH_PASSWORD=password  # (OPTIONAL - if not set no password used)
```

or with docker run
```bash
docker run --rm -p 5678:5678 appwrite/resque-web:v1.0.0  
```

## Build
```bash
docker build -t appwrite/resque-web:1.0.0 .
```

## Push
```bash
docker push appwrite/resque-web:1.0.0
```

## Find Us

* [GitHub](https://github.com/appwrite)
* [Discord](https://discord.gg/GSeTUeA)
* [Twitter](https://twitter.com/appwrite_io)

## Copyright and license

The MIT License (MIT) [http://www.opensource.org/licenses/mit-license.php](http://www.opensource.org/licenses/mit-license.php)
