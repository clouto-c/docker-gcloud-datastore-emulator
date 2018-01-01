# Google Cloud Datastore Emulator Image


## Usage

The following shell statement show the most simple execution of the provided image.

```bash
docker run --rm --tty --interactive -e CLOUDSDK_CORE_PROJECT='something_project' \
 --publish 8181:8181 clouto/docker-gcloud-datastore-emulator start --consistency=1.0 \
 --host-port=0.0.0.0:8181 --no-store-on-disk
```

The following example shows how to configure the Emulator to be used in a Wercker development pipeline.

```yaml
dev:
  services:
    - name: datastore
      id: clouto/docker-gcloud-datastore-emulator
      cmd: start --consistency=1.0 --host-port=0.0.0.0:8181 --no-store-on-disk
      env:
        CLOUDSDK_CORE_PROJECT: something_project
  steps:
    - script:
        name: Define Datastore environment variables
        code: |
          ADDR=$DATASTORE_PORT_8181_TCP_ADDR
          PORT=$DATASTORE_PORT_8181_TCP_PORT
          export DATASTORE_EMULATOR_HOST=$ADDR:$PORT
```
