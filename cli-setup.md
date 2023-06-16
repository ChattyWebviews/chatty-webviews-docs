---
title: CLI setup
layout: home
nav_order: 2
---

# CLI Setup

Chatty Webviews' Command Line Interface (CLI) is an indispensable tool that streamlines the process of releasing over-the-air updates to your application's users. With it, there's no need to go through Google's Play Store or Apple's AppStore, making it ideal for rapid deployment of critical security fixes and other application updates.

## Prerequisites

To utilize the Chatty Webviews CLI, which is completely free and open source, you need to have your own Firebase account set up, with the appropriate services enabled and environment variables defined. If you haven't done this yet, please follow our [Backend Setup Guide](https://docs.chattywebviews.com/backend-setup.html) before proceeding.

## Installation

To install Chatty Webviews CLI, simply run the following command in your terminal:

```bash
npm install -g @chatty-webviews/cli
```

## Environment Variables

The following environment variables need to be defined on your machine or in your Continuous Integration/Continuous Deployment (CI/CD) pipeline for the CLI to operate properly:

```bash
export FIREBASE_API_KEY="<your_api_key>"
export FIREBASE_AUTH_DOMAIN="<your_auth_domain>"
export FIREBASE_PROJECT_ID="<your_project_id>"
export FIREBASE_STORAGE_BUCKET="<your_storage_bucket>"
export FIREBASE_APP_ID="<your_app_id>"
```
These environment variable values can be found in your Firebase account's Project settings.

## CLI Commands

With your Firebase infrastructure and Chatty Webviews CLI set up, you're ready to release over-the-air updates to your app users. Stay tuned for our upcoming detailed guide on how to use the CLI commands.

**Note:** Always make sure you have the latest version of the Chatty Webviews CLI installed. This ensures that you always have access to the latest features and security updates. 

With this setup, distributing new app versions to your users becomes a straightforward and simplified process.