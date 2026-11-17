# Solmi Sensor

Open source of Solmi Sensor, application ID `ru.solmi.sensor`, based on JugglucoNG and Juggluco. GNU GPLv3 and the existing upstream copyright notices apply; see [LICENSE.txt](LICENSE.txt) and the source headers.

Public project identity: [SolmiApp](https://github.com/SolmiApp). The organization release/update channel must be provisioned and verified before an official installer is published. This source snapshot itself is not a tested installer or a completed release.

## Source and provenance

The complete original project README, credits and documentation links are preserved in [UPSTREAM_README.md](UPSTREAM_README.md). Its upstream download links refer to upstream software. Solmi Sensor has its own application ID, signing identity and update channel.

This public source tree preserves the pinned libjuice submodule and Git symbolic links. Initialize submodules after cloning with `git submodule update --init --recursive`.

## Independent builds

The inherited toolchain requires JDK 21, the Android SDK/NDK and CMake versions recorded in the Gradle files. A local fork without external signing settings uses the standard Android debug identity. Such a build cannot update an official Solmi Sensor installation. Configuration has been checked offline; complete Kotlin/native compilation and device behavior have not been verified for this snapshot.

Signing stores and private cloud-service credentials are excluded. AiDex CN cloud access needs `SOLMI_SENSOR_AIDEX_APP_SECRET` and `SOLMI_SENSOR_AIDEX_PRIVATE_KEY` supplied through the private build environment or local Gradle properties. Values must never be committed. A build without these inputs does not provide that cloud integration.

## Official updates

Official builds must retain the existing private signing identity. The `requireProductionSigning` guard rejects missing signing settings or private service inputs. No signing key is generated or included by this repository. The inherited distribution scripts have not been validated for the current Solmi version scheme; a verified official build workflow is still required.

The Sensor updater retains its schema 1 manifest with an `artifacts` array and the `solmi-sensor.apk` filename. It is separate from the main Solmi application's update format. Public releases are intended to be published by the real GitHub Actions bot under SolmiApp after verification.

The inherited experimental-software warning and licensing notices remain in the upstream documentation and source.
