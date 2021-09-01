# crystal-helloworld

This simple web server, just replies with the time
and a "hello world" message.

It is meant to be used for a Cloud Run demo.

If you are not familiar with Crystal, it is very similar
to the Ruby language, but it is compiled.  The following
docker image is only a few MB in size.

## Build a docker container, using docker
docker build -t crystal-web-server:0.1 .

## Build using Cloud Build, then push to GCR/Artifact
gcloud builds submit --tag [IMAGE] 

gcloud run deploy crystal-webserver --image [IMAGE]

or

```gcloud beta run deploy crystal-webserver --source . \
--platform managed --allow-unauthenticated```

## Execute on Cloud Run
```gcloud run deploy crystal-webserver --image <Cloud Artifact/Registry> \
--platform managed --allow-unauthenticated```

## Clean up
gcloud run services delete crystal-webserver
