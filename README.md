###About
Collections of my docker images. For public.
Base GNU/Linux image distribution - [baseimage](https://github.com/phusion/baseimage-docker)

###List

 * java.base - java 8 base image.

###Docker example

```bash
docker build -t java.base:1.0.0 --rm --no-cache --force-rm .
docker exec -i -t java.base bash
```
