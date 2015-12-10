# drone-heroku

[![Build Status](http://beta.drone.io/api/badges/drone-plugins/drone-heroku/status.svg)](http://beta.drone.io/drone-plugins/drone-heroku)
[![](https://badge.imagelayers.io/plugins/drone-heroku:latest.svg)](https://imagelayers.io/?images=plugins/drone-heroku:latest 'Get your own badge on imagelayers.io')

Drone plugin for deploying to Heroku

## Usage

```sh
./drone-heroku <<EOF
{
    "repo": {
        "clone_url": "git://github.com/drone/drone",
        "full_name": "drone/drone"
    },
    "build": {
        "event": "push",
        "branch": "master",
        "commit": "436b7a6e2abaddfd35740527353e78a227ddcb2c",
        "ref": "refs/heads/master"
    },
    "workspace": {
        "root": "/drone/src",
        "path": "/drone/src/github.com/drone/drone"
    },
    "vargs": {
        "app": "awesome",
        "force": true,
        "commit": true
    }
}
EOF
```

## Docker

Build the Docker container using `make`:

```sh
make deps build
docker build --rm=true -t plugins/drone-heroku .
```

### Example

```sh
docker run -i plugins/drone-heroku <<EOF
{
    "repo": {
        "clone_url": "git://github.com/drone/drone",
        "full_name": "drone/drone"
    },
    "build": {
        "event": "push",
        "branch": "master",
        "commit": "436b7a6e2abaddfd35740527353e78a227ddcb2c",
        "ref": "refs/heads/master"
    },
    "workspace": {
        "root": "/drone/src",
        "path": "/drone/src/github.com/drone/drone"
    },
    "vargs": {
        "app": "awesome",
        "force": true,
        "commit": true
    }
}
EOF
```
