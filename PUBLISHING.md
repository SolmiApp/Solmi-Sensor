# Solmi Sensor release channel

The public source remains on `main`. Signed APK releases are published only by the guarded GitHub Actions workflow from an immutable artifact commit containing exactly `solmi-sensor.apk` and `update-manifest.json`.

The workflow validates the complete candidate tree, package name, version, minimum SDK, SHA-256 and the established signing certificate. It creates a draft, checks that the author is `github-actions[bot]`, downloads both assets, verifies them again, and only then publishes the release. Signing keys are never stored in this repository or required by the publisher.
