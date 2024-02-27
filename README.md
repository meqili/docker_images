# docker_images

## debug
**Error**: 
`2024-02-27T20:52:24.638385864Z exec /usr/bin/sh: exec format error`

**Solution**:
docker build --platform="linux/amd64" -t container_name  .
