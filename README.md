# lemmy-metric-multiarch

[![Build Multiarch Images](https://github.com/ubergeek77/lemmy-docker-multiarch/actions/workflows/build-multiarch.yml/badge.svg?branch=main)](https://github.com/ubergeek77/lemmy-docker-multiarch/actions/workflows/build-multiarch.yml)

A build repository for metrics-capable and multiarch Docker images for Lemmy.

I enable prometheus metrics by setting the `prometheus-metrics` feature at build time.
See [the official docs](https://join-lemmy.org/docs/administration/prometheus.html) for more details.

Builds [`LemmyNet/lemmy`](https://github.com/LemmyNet/lemmy/) and [`LemmyNet/lemmy-ui`](https://github.com/LemmyNet/lemmy-ui/) for:

- x64 (`amd64`)
- ARM (`arm/v7`)
- ARM64 (`arm64`)

Other than for
- metrics enabled
- multi-arch builds
- GHCR docker registry (so no rate limiting like with Dockerhub)

They are the same as the official upstream images, so they can act as a drop-in replacement. You are welcome to use these.

When [`LemmyNet/lemmy`](https://github.com/LemmyNet/lemmy/) or [`LemmyNet/lemmy-ui`](https://github.com/LemmyNet/lemmy-ui/) have new tags, my workflow will automatically be launched and those new tags will be built.

I don't tag `latest`, so you will need to specify a tag to pull. For example, to use `0.18.0`:

```
ghcr.io/cottand/lemmy:0.18.0
ghcr.io/cottand/lemmy-ui:0.18.0
```

I also build `rc` tags. In general, I will have images for any stable or `rc` tag of the official Lemmy repositories. To see the full list of tags I've built, check the Packages section on this repo, or go to the images directly:

- https://github.com/cottand/lemmy-docker-multiarch/pkgs/container/lemmy
- https://github.com/cottand/lemmy-docker-multiarch/pkgs/container/lemmy-ui


This repo is forked from [ubergeek77/lemmy-docker-multiarch](https://github.com/ubergeek77/lemmy-docker-multiarch),
which builds the same images for multi-arch but does not enable the prometheus metrics feature - so
credit goes to @ubergeek77 for that.