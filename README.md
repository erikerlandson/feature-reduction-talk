# feature-reduction-talk
Notebook image and notebook for feature reduction talk

### Build Images
```bash
$ cd /path/to/feature-reduction-talk
$ docker build --no-cache -f Dockerfile-spark -t manyangled/openshift-spark-fr:latest .
$ docker build --no-cache -f Dockerfile-notebook -t manyangled/feature-reduction-talk:latest .
$ docker push registry/openshift-spark-fr:latest
$ docker push registry/feature-reduction-talk:latest
```

### Run
Run the notebook image in openshift:
```bash
$ oc run frnb --image=registry/feature-reduction-talk:latest --expose --port=8888
```
Expose a route to the notebook so you can hit it from a browser.

Use the Oshinko web-ui to create a spark cluster, named `frclust`, and using image `registry/openshift-spark-fr:latest`
