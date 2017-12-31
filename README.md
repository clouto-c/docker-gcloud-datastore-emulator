# Google Cloud Datastore Emulator Image


## Usage

The following shell statement show the most simple execution of the provided image.

```bash
docker run --rm --tty --interactive -e CLOUDSDK_CORE_PROJECT='something_project' \
 --publish 8181:8181 clouto/docker-gcloud-datastore-emulator start --consistency=1.0 \
 --host-port=0.0.0.0:8181 --no-store-on-disk
```

The following example shows how to configure the Emulator to be used in a Wercker pipeline.

```yaml
box: ruby:2.4.1
services:
  - id: clouto/docker-gcloud-datastore-emulator
    cmd: start --consistency=1.0 --host-port=0.0.0.0:8181 --no-store-on-disk
    env:
      CLOUDSDK_CORE_PROJECT: something_project
```
