# Manifest Schema

`deploy.manifest.json` is the contract between `@angular-yc/cli` and Terraform.

## Root Fields

- `schemaVersion`: currently `"1.0"`
- `buildId`: unique build identifier
- `timestamp`: ISO datetime
- `angularVersion`: detected Angular version
- `projectName`: workspace project name
- `capabilities`: analyzer output
- `routing`: API Gateway/OpenAPI routing model
- `artifacts`: packaged files and entrypoints
- `responseCache`: optional response cache config (S3 + YDB)
- `environment`: optional env/secrets metadata
- `deployment`: function sizing and region

## Capabilities

- `ssr`: SSR enabled flag, entrypoint, adapter mode, standalone bundle status
- `prerender`: enabled flag, route list, discovery source
- `api`: express API metadata (`/api` base and discovered routes)
- `rendering`: lazy loading, standalone mode, hydration, signals, zoneless state
- `assets`: image optimization flags (`NgOptimizedImage`, `_image` function need)
- `responseCache`: TTL/SWR/purge/tag config

## Artifacts

- `artifacts.assets`: static output (`browser/`, optional `prerender/`)
- `artifacts.server`: `server.zip` + `index.handler` entrypoint (when SSR/API enabled)
- `artifacts.image`: `image.zip` + handler (when image optimization enabled)

## Response Cache

Replaces ISR semantics for Angular:

- body/html cached in Object Storage
- metadata/tags/ttl tracked in YDB
- purge endpoint path (`/api/__cache/purge`) with auth mode
