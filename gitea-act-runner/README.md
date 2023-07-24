# gitea-act-runner

A runner for Gitea based on act.

## Important step when deploying
When the runner loops not being able to read the file `/config/config.yaml`, enter the container and execute
```bash
touch /config/config.yaml
```
