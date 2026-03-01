# Migration from Angular Universal

Guide to migrate existing Angular SSR projects.

1. Keep your existing Angular SSR app structure and Express entry point.
2. Replace custom deployment scripts with either:
   - `angular-yc bootstrap` + `angular-yc deploy` (recommended), or
   - explicit `angular-yc analyze/build/upload` + Terraform apply flow.
3. Adopt manifest-driven Terraform module inputs for repeatable environments.
4. Configure response cache settings where you previously used ad-hoc SSR caching logic.
