---
name: Feature request
about: Suggest a new feature in termux-api-package
title: ''
labels: ''
assignees: ''

---

**Feature description**
Describe the feature and why you want it.

**Background information**
Have you checked if the feature is accessible through the android API?
Do you know of other open-source apps that has a similar feature as the one you want? (Provide links)


name: CI Workflow

on:
  push:
    branches:
      - main
  pull_request:
    branches:
      - main

jobs:
  build-and-test:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v3

      - name: Set up Node.js
        uses: actions/setup-node@v3
        with:
          node-version: 21

      - name: Install dependencies
        run: npm install

      - name: Run tests
        run: npm test