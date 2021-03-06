# Complete Asciidoctor toolchain including Pygments

Uses the official Asciidoctor Docker image https://hub.docker.com/r/asciidoctor/docker-asciidoctor at tag `latest` as the base image and patches it as follows:

- update the index of available apk packages
- upgrade installed apk packages
- install Python2 via apk, which Pygments requires
- install the Pygments syntax highlighter gem

Otherwise behaves like the base image - so see the docs over there. But in short, for example:
```
docker run --rm --name asciidoctor -t \
           -v $(pwd):/documents       \
           integrational/asciidoctor:latest asciidoctor-pdf index.adoc
```
