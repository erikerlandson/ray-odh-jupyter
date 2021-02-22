# ray-odh-jupyter

jupyter notebook images for Open Data Hub, with ray libraries pre-installed

### Build ray-minimal-notebook

These environment variable settings build without Thoth advising.
For an example of turning on Thoth-advise see
[here](https://github.com/thoth-station/s2i-minimal-notebook#building-the-minimal-notebook).

```bash
$ cd /path/to/ray-odh-jupyter
$ ./scripts/podman-s2i-dir images/ray-minimal-notebook quay.io/erikerlandson/ray-minimal-notebook:latest quay.io/thoth-station/s2i-minimal-notebook:latest --env ENABLE_PIPENV=1 --env THOTH_ADVISE=0 --env THOTH_ERROR_FALLBACK=1 --env THOTH_DRY_RUN=1 --env THOTH_PROVENANCE_CHECK=0
```

