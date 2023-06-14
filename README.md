# Build keycloak image based on keycloak-22 source

This repository contains workflow to build and push base image for
Keycloak 22 using the source in the following github repo:
* https://github.com/RHEcosystemAppEng/keycloak.git (_branch keycloak-22_)

### Prerequistes

* The workflow needs following variables (and secrets) in the defined environment:
  * IMAGE_NAME
  * IMAGE_TAG
  * KEYCLOAK_VERSION
  * QUAY_USER
  * REPO_BRANCH
  * REPO_NAME
  * REPO_OWNER
* Following secret is also needed in the defined environment:
  * QUAY_PASS
* _Correct values have already been provided for all these variables, but they are provided
  here in case any of the values needs to be modified._

## Run the workflow
To run the workflow that builds and pushes a base-image using the keycloak source, either
push in this repo or go to the workflow named `build-image` and manually `Run the workflow`