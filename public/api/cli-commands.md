# CLI Commands

## `angular-yc analyze`

Analyze an Angular workspace and generate capability metadata.

```bash
angular-yc analyze --project . --output ./analysis --verbose
```

## `angular-yc build`

Build and package artifacts for deployment (`server.zip`, `image.zip`, assets, OpenAPI, manifest).

```bash
angular-yc build --project . --output ./build
```

## `angular-yc deploy-manifest`

Validate or reconstruct `deploy.manifest.json` from build artifacts.

```bash
angular-yc deploy-manifest --build-dir ./build --out ./build/deploy.manifest.json
```

## `angular-yc upload`

Upload build artifacts to Yandex Object Storage.

```bash
angular-yc upload \
  --build-dir ./build \
  --bucket my-assets-bucket \
  --prefix build-123 \
  --cache-bucket my-cache-bucket
```

## `angular-yc plan`

Show deployment plan without building or uploading.

```bash
angular-yc plan --project . --verbose
```
