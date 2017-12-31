# Google Cloud Datastore Emulator Image

# Usage
The following example shows how to configure the Emulator to be used in a Wercker pipeline.

```yaml
box: ruby:2.4.1
services:
  - id: clouto/docker-gcloud-datastore-emulator
    cmd: start --consistency=1.0 --host-port=127.0.0.1:8181 --no-store-on-disk
    env:
      CLOUDSDK_CORE_PROJECT: something_project
```
