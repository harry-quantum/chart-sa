## Create a local chart

```bash
$ helm create chart-sa
cd chart-sa
```

## Verify the chart files are valid

```bash
helm lint .
helm template .
```

The cmds validate the files on your local machine.


## Init the helm

Use the following cmd to init helm, which will install tiller on the cluster targeted by the current kubectl context:

```bash
helm init
```

## Installing the Chart
To install the chart with the release name `sa`:

```bash
$ helm install --name sa .
```

> **Tip**: List all releases using `helm ls -a`

## Uninstalling the Chart

To uninstall/delete the `sa` deployment:

```bash
$ helm delete sa
```

The command removes all the Kubernetes components associated with the chart and deletes the release.

## Updating a reelase

```bash
$ helm repo update hw .
```

 The command does not seem to make any changes. It seems helm is a bit buggy in the area of updating resources.

## Checking the deployment change:

```bash
$ kubectl get deploy/hw-hello-world -o yaml
```

## Installing a chart from a repo

We can install charts from repo directly.

```bash
helm repo add bitnami https://charts.bitnami.com/bitnami
helm install --name mywebserver bitnami/nginx
helm delete mywebserver
```

## Downloading a chart from repo

Sometimes we want to download a chart for study. We can use the following cmds to do this:

```bash
helm fetch bitnami/nginx
tar -xvf nginx-3.2.0.tgz
``` 