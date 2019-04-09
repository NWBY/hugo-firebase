# Dockerfile with Hugo and Firebase:fire:

This dockerfile comes with the static-site generator Hugo and Firebase tools installed.

Personally used on my own website: https://nwby.io/

This image uses Hugo version 0.53 and will automatically install the latest version of Firebase.

# Usage

Example usage on Gitlab Runner:
```
image: nwbyio/hugo-firebase

before_script:
  - hugo version
  - firebase --version

stages:
  - deploy
  
pages:
  stage: deploy
  script:
    - hugo
    - firebase deploy --token $FIREBASE_DEPLOY_TOKEN --only hosting --project PROJECT_NAME
  artifacts:
    paths:
      - public
```
Running the version commands for hugo and firebase will allow you to see that you have the latest version of these tools installed.
