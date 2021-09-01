# crystal-helloworld

This simple web server, just replies with the time
and a "hello world" message.

It is meant to be used for a Cloud Run demo.

If you are not familiar with Crystal, it is very similar
to the Ruby language, but it is compiled.  The following
docker image is only a few MB in size.

## Build a docker container, using docker
``` bash
docker build -t crystal-web-server:0.1 .
```

## Build using Cloud Build (automatically pushed to GCR)
``` bash
gcloud builds submit --tag gcr.io/PROJECT_ID/IMAGE_NAME
gcloud run deploy crystal-webserver --image [IMAGE]
```

or

### Build, push (to Artifact Registry) and deploy in one command
``` bash
gcloud beta run deploy crystal-webserver --source . \
--platform managed --allow-unauthenticated
```

## Execute on Cloud Run
``` bash
gcloud run deploy crystal-webserver --image <Cloud Artifact/Registry> \
--platform managed --allow-unauthenticated
```

## Clean up
``` bash
gcloud run services delete crystal-webserver
```
