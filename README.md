# Docker image with Go + librdkafka

Build/tool image with Go 1.12, librkafaka and build tools (git, gcc, make...) installed and ready to run.

Useful to run tests in CI and as base image for multi-stage builds.

There are two images available, based on Alpine (default) and Debian stretch.

If you plan to run tests with `ginkgo` and race detection enabled there's an issue with [Alpine](https://groups.google.com/forum/#!topic/golang-nuts/WnfKCoaRP_E).
The Debian stretch must be used for this use case.
