# Quick Start

From an Angular SSR project:

```bash
angular-yc analyze --project . --verbose
angular-yc build --project . --output ./build
angular-yc upload --build-dir ./build --bucket <assets-bucket> --prefix <build-id>
```

Then apply Terraform with the generated manifest path.
