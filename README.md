# API CP Audit Reports Service

This repository contains the API definition for the Audit Reports service.

## Documentation

For further documentation on how this repository is structured see the [API Template repository](https://github.com/hmcts/api-cp-template).

### Contribute to This Repository

Contributions are welcome! Please see the [CONTRIBUTING.md](.github/CONTRIBUTING.md) file for guidelines.

## License

This project is licensed under the [MIT License](LICENSE).

## Team Branch Publication

The non-release workflow builds pushes to `team/**` and PRs targeting `team/**`.
Publication is allowed for team pushes and same-repository team PRs, but not fork
PRs or PRs targeting main/master. The workflow changes must exist on the team
branch itself; a fix merged only into main does not update that branch.

This API contract project publishes a Maven JAR, not a container image:
`uk.gov.hmcts.cp:api-cp-audit-reports:<version>`. Destinations are the Azure
Artifacts `hmcts-lib` feed and GitHub Packages, not ACR or direct Artifactory
publication. The service consumes the published contract version as a Gradle
dependency.

Use the exact version printed in the successful publication job summary. Draft
versions include the run ID/attempt (and PR number for PR builds), avoiding
collisions between repeated builds. Green build checks with a skipped Publish
job do not establish that a package was published. Maven credentials are checked
before publishing and remain environment variables, not command-line arguments.
