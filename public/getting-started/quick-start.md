# Quick Start

Recommended flow (uses CLI config + env overrides):

```bash
angular-yc bootstrap --config ./angular-yc-cfg.json --auto-approve
angular-yc deploy --config ./angular-yc-cfg.json --auto-approve
```

This runs analyze/build/upload/apply under a single deploy contract.

If you need explicit control, use the 4-step flow:

```bash
angular-yc analyze --project . --verbose
angular-yc build --project . --output ./build
angular-yc upload --build-dir ./build --bucket <assets-bucket> --prefix <build-id>
# then apply Terraform module angular_yc
```
