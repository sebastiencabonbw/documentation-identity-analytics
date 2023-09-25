# Documentation Identity Analytics

## Introduction

This repository holds the documentation for Identity Analytics.  
The documentation is used as an input to build the documentation [https://developer.radiantlogic.com/](https://developer.radiantlogic.com/)

## Repository Structure

The repository is structured such as each branch corresponds to the documentation of a specific version.  

## Gatsby .env

To use the repository to build locally in Gatsby use the following code in the `GATSBY_DEPLOY_REPOS` parameter of the `.env` file (some adaptation may be necessary):

```json
GATSBY_DEPLOY_REPOS='
[
  {
    "name": "bw",
    "displayName": "Identity Analytics",
    "description": "XXXX",
        "links": [
      {
        "text": "Self Managed - docker",
        "href": "/bw/main/#0"
      }
    ],
    "remote": "https://github.com/radiantlogic-v8/documentation-identity-analytics.git",
    "patterns": [
      "home-pages/**",
      "documentation/**"
    ],
    "deployBranches": [
      {
        "name": "iap-1.8",
        "displayName": "Identity Analytics"
      }
    ]
  }
]
'

```
