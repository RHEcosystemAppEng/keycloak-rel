# Build keycloak image based on keycloak-22 source

This repository contains workflow to build and push base image for
Keycloak 22 using the source in the following github repo:
* https://github.com/RHEcosystemAppEng/keycloak.git (_branch keycloak-22_)

### Prerequistes

* The workflow needs following variables (and secrets) in the defined environment:
  * CREATE_IMAGE_NOTIFIERS
    * Comma separated list of emails addresses that will be notified on successful completion of the GitHub Action workflow
  * EMAIL_SENDER_NAME
    * User friendly name (not email) of the sender. Value from `MAIL_USER` is always shown next to this name in the email
  * IMAGE_NAME
  * IMAGE_TAG
  * KEYCLOAK_VERSION
    * keycloak build results in a tarball with this version
  * QUAY_USER
    * _quay.io login uses this user_
  * QUAY_REPO_OWNER
    * _image will be pushed to the repo owned by this user/org_
  * REPO_BRANCH
  * REPO_NAME
  * REPO_OWNER
  * CREATE_IMAGE_NOTIFIERS
    * Comma separated list of email addresses that will be notified on successful completion of this workflow
  * WORKFLOW_USER_SUFFIX
    * Added to the value of github actor - for git username when pushing a new tag
  * WORKFLOW_EMAIL_DOMAIN
    * Added to the value of workflow user - for git email when pushing a new tag, and email from address when sending successful notification
* Following secret is also needed in the defined environment:
  * QUAY_PASS
    * _quay.io login uses this password_
  * ACTIONS_PAT
    * _used for performing push operations on the source repo_
  * MAIL_USER
    * _used for sending email notification on successful completion of the workflow_
  * MAIL_PASS
    * _used for sending email notification on successful completion of the workflow_
  

  _Correct values have already been provided for all these variables, but they are provided
  here in case any of the values needs to be modified. Only people with proper access will
  be able to modify these environment secrets/variables._


## Run the workflow
To run the workflow that builds and pushes a base-image using the keycloak source, either
push in this repo or go to the workflow named `build-image` and manually `Run the workflow`
