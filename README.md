# Expo Hello World

This is a minimal Expo project that renders a simple Hello World screen.

## What is Expo?

Expo is a toolchain and platform for building React Native apps with a fast local development workflow. It provides project scaffolding, a development server, bundling, and optional native build tooling.

## What is Expo Go?

Expo Go is the mobile app for iPhone and Android that lets you open and test an Expo project directly from a local development server without creating a native build first.

## Run locally

Install dependencies:

```bash
npm install
```

Start the Expo development server:

```bash
npm start
```

Run in the browser:

```bash
npm run web
```

Open on iPhone with Expo Go:

1. Make sure the phone and computer are on the same network.
2. Start the app with `npm start -- --lan`.
3. Scan the QR code from the terminal in Expo Go.

# CodeBuild IAM Policy – Setup Guide

This document describes how to configure IAM permissions for AWS CodeBuild projects used in TrimCoach deployments.

Each environment (`test`, `staging`, `production`) must have its own policy with environment-specific values.

## Overview

The CodeBuild service role must be allowed to:
- Read and write objects in the environment S3 bucket
- List the S3 bucket
- Create CloudFront invalidations for the environment distribution

## Setup Steps

1. Identify the environment (e.g. `test`, `staging`, `production`)

2. Determine required values:
   - **S3 bucket name** (example: `ungap-expo-test`)
   - **AWS account ID** (example: `471112617922`)
   - **CloudFront distribution ID** (example: `E1S709XQKON91E`)

3. Replace the placeholders in the policy below:
   - `<BUCKET_NAME>`
   - `<AWS_ACCOUNT_ID>`
   - `<CLOUDFRONT_DISTRIBUTION_ID>`

4. Attach the policy to the CodeBuild service role

## IAM Policy Template

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "S3DeployToEnvironmentBucket",
      "Effect": "Allow",
      "Action": [
        "s3:ListBucket"
      ],
      "Resource": "arn:aws:s3:::<BUCKET_NAME>"
    },
    {
      "Sid": "S3ObjectDeployToEnvironmentBucket",
      "Effect": "Allow",
      "Action": [
        "s3:GetObject",
        "s3:PutObject",
        "s3:DeleteObject",
        "s3:PutObjectTagging",
        "s3:PutObjectAcl"
      ],
      "Resource": "arn:aws:s3:::<BUCKET_NAME>/*"
    },
    {
      "Sid": "CloudFrontInvalidation",
      "Effect": "Allow",
      "Action": [
        "cloudfront:CreateInvalidation"
      ],
      "Resource": "arn:aws:cloudfront::<AWS_ACCOUNT_ID>:distribution/<CLOUDFRONT_DISTRIBUTION_ID>"
    }
  ]
}


