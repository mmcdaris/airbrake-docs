---
layout: classic-docs
title: Bitbucket
categories: [integrations]
description: Bitbucket
---
> **NOTE:** This doc is only for our cloud service. [See Bitbucket
> integration doc for on-premise
> installations](/docs/on-premise/bitbucket-integration).

Adding the Airbrake-Bitbucket integration will create Bitbucket issues for new
Airbrake errors.
The default behaviour is to automatically create a Bitbucket issue when a new
type of error is reported to Airbrake, this can be turned off if you prefer to
create a Bitbucket issue from an Airbrake error manually.

### What information is in a created issue?

A Bitbucket issue created from an Airbrake error includes a lot of helpful
information. It links back to the Airbrake error, displays the error type and
message, shows where and when the error occurred, and more. Here is an example of
a created issue:

![example-issue](/docs/assets/img/docs/integrations/bitbucket_example_issue.png)

## How to add the Bitbucket integration
### Authenticate with Bitbucket
Airbrake needs permission to create Bitbucket issues for your project, so the
first step is to authenticate!

1. Click **Integrations** for your project
2. Click **Bitbucket**
3. Click **Redirect to Bitbucket for authentication**

![bitbucket auth](/docs/assets/img/docs/integrations/bitbucket_auth.png)

### Add Bitbucket integration
Add your Bitbucket account name and project's repository name then **save**.

![bitbucket settings](/docs/assets/img/docs/integrations/bitbucket_settings.png)
