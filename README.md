# charts

custom chart repository for helm (kubernetes package manager)

## Enable repository

We are using [github-pages](https://pages.github.com/) for storing helm [packages](https://github.com/Vnet-as/charts/tree/gh-pages/charts). To enable this repository execute following commands:

```bash
$ # add this repository to repository list
$ helm repo add vnet https://vnet-as.github.io/charts/charts
```

```bash
$ # update package list
$ helm repo update
```
