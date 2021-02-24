# ray-odh-jupyter

jupyter notebook images for Open Data Hub, with ray libraries pre-installed

### Build ray-minimal-notebook

These environment variable settings build without Thoth advising.

```bash
$ cd /path/to/ray-odh-jupyter
$ ./scripts/podman-s2i-dir \
    images/ray-minimal-notebook quay.io/erikerlandson/ray-minimal-notebook:latest \
    quay.io/thoth-station/s2i-minimal-notebook:latest \
    --env ENABLE_PIPENV=1 \
    --env THOTH_ADVISE=0 \
    --env THOTH_ERROR_FALLBACK=1 \
    --env THOTH_DRY_RUN=1 \
    --env THOTH_PROVENANCE_CHECK=0
```

Here is an example of building with Thoth enabled.
The environment variable `THAMOS_CONFIG_TEMPLATE` is being used
to automatically probe the runtime environment and generate a
`.thoth.yaml` config on the fly.

For more information refer to this
[example repo](https://github.com/thoth-station/s2i-example)

```bash
./scripts/podman-s2i-dir \
    images/ray-minimal-notebook quay.io/erikerlandson/ray-minimal-notebook:latest \
    quay.io/thoth-station/s2i-minimal-notebook:latest \
    --env ENABLE_PIPENV=1 \
    --env THOTH_ADVISE=1 \
    --env THOTH_DRY_RUN=0 \
    --env THOTH_PROVENANCE_CHECK=1 \
    --env THAMOS_CONFIG_TEMPLATE='thoth-conf-template.yaml'
```
