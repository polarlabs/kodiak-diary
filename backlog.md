This is our backlog. Actions items are listed in descending priority.

# Kodiak Web Server

:pencil: Kodiak Web Server: use CI / CD for artifact build and Dockerfile for image build.

:pencil: Implement TLS with Let's Encrypt for the Kodiak web server.

:pencil: Implement a permanent redirect from HTTP to HTTPS for the Kodiak web server.

:pencil: Sum up generic best practices to build and publish software.

:pencil: Add the version of the Kodiak Web Server to the Kodiak Web Client UI.

:pencil: Document how Kodiak projects set version, build and build metadata.

# Configuration Management

:pencil: Describe the concept of configuration management in the [Kodiak KB](https://github.com/polarlabs/kodiak-kb).

* Enroll: must be robust => low change frequency + independent, even accepting some redundancies.
* Prefer pull to push
* Differentiate fixing deviations from a baseline from ongoing changes.
* Consider singularly applied changes.

# Other topics

:pencil: Write an article in Kodiak KB describing the approach for testing.

:pencil: Adopt GitHub Actions of Kodiak web client to branching model.

:pencil: Review Kodiak KB articles about build numbers.

:pencil: Add an example to factory on how to use the tag-ref-as-build workflow.

:pencil: Add an article about ISP selection process to the [Kodiak KB](https://github.com/polarlabs/kodiak-kb).

:pencil: Add an article about netcup to the [Kodiak KB](https://github.com/polarlabs/kodiak-kb).

:pencil: Add an article about Ansible to the [Kodiak KB](https://github.com/polarlabs/kodiak-kb), including the ansible-pull, ansible-lint and integration into IDE.

:pencil: Develop a CI / CD approach covering all defined branches.

Kodiak Web Client:

Branch   Action
feat/*   *
=> backup and exchange only

dev          pull merge
=> build with build number
=> store artifact
=> trigger kodiak-web-server with dev => publish image:dev in registry

rel/*.*.*    create branch, push
=> build with build number
=> store artifact
=> trigger kodiak-web-server with rel/* => publish image:rel/* in registry

main         not pull, but create tag v/*.*.*
=> build with build number
=> store artifact
=> trigger kodiak-web-server with v/*.*.* => publish image:v/*.*.* und :latest in registry

patch/*.*.*  create branch, push
=> build with build number
=> store artifact
=> trigger kodiak-web-server with patch/*.*.* => publish image:patch/*.*.* in registry
