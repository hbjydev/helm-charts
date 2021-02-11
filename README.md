# Hayden's Helm Charts

My personal Helm Charts repo, containing charts for software I build as well as
software I use that don't have existing charts.

## Using the repo

To use this repository, simply add the repo to your Helm install and update the
repo cache.

```shell
$ helm repo add hbjy https://helm.hbjy.dev
$ helm repo update
```

Now, you can use the repo's charts as you would with any other charts.

```shell
$ helm install cardinal hbjy/cardinal -f config.yml
```

## Contributing

The repo should automatically re-generate the repo index on every push of the
`main` branch, so if you have a change, submit a PR, and if I merge it, your
chart version will automatically be added to the chart repository.

