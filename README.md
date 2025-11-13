# wakewords

created using 

https://github.com/TaterTotterson/microWakeWord-Trainer-Nvidia-Docker

docker-compose.yaml

```yaml
services:
  microwakeword:
    deploy:
      resources:
        reservations:
          devices:
            - driver: nvidia
              count: 1
              capabilities: [gpu]
    image: ghcr.io/tatertotterson/microwakeword:latest
    container_name: microwakeword
    volumes:
      - ./data:/data
    ports:
      - 8899:8888
    restart: unless-stopped
```
