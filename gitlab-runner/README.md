## Run Command

```
docker run -d --name gitlab-runner --restart always \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v /srv/gitlab-runner/config:/etc/gitlab-runner \
  gitlab/gitlab-runner:latest
```

## Register Runner

```
docker run -it --rm -v /srv/gitlab-runner/config:/etc/gitlab-runner gitlab/gitlab-runner register
```
