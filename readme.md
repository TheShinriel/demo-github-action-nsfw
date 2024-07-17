# NSFW Content Detection CI/CD Pipeline

This repository demonstrates the implementation of a Continuous Integration and Continuous Deployment (CI/CD) pipeline using GitHub Actions to automatically detect not-safe-for-work (NSFW) content in images upon every push to the repository.

## Overview

The GitHub Actions workflow defined in this repository utilizes the `fabasoad/nsfw-detection-action` to scan images for NSFW content. It sets a high threshold to minimize false positives, ensuring that only content with a high probability of being NSFW is flagged.

## Workflow

The workflow triggers on every `push` event to the repository. It runs on the latest Ubuntu environment and checks for added, modified, or renamed JPEG and JPG images. If NSFW content is detected in any of these images above a set threshold, appropriate actions can be taken, which should be defined in the workflow according to your project's needs.

## Setup

### Prerequisites

- A GitHub account.
- A repository where you want to implement this workflow.
- A Cloudmersive API key to use the NSFW detection service.

### Configuration

1. **Cloudmersive API Key**: You need to obtain an API key from Cloudmersive. Store this key in your repository's secrets as `CLOUDMERSIVE_API_KEY`.

2. **GitHub Token**: The workflow uses the built-in `GITHUB_TOKEN` secret for authentication within GitHub Actions.

### Adding Workflow to Your Repo

To use this workflow in your repository, follow these steps:

1. Create a `.github/workflows` directory in your repository if it does not already exist.
2. Add a new file named `nsfw-detection.yml`.
3. Copy and paste the YAML content from above into this file.
4. Ensure that your repository's secrets are set up with your `CLOUDMERSIVE_API_KEY`.

## Usage

Once set up, the workflow runs automatically upon each push to your repository. If any images committed to the repo meet the criteria for NSFW content, further actions can be tailored based on the outcome.

## Customization

You can customize the workflow by adjusting the threshold, changing the file types monitored, or altering the events that trigger the workflow.

## Support

For more information about the `fabasoad/nsfw-detection-action`, visit the [official documentation](https://github.com/fabasoad/nsfw-detection-action?tab=readme-ov-file).
