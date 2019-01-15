[![Build Status](https://travis-ci.org/cfn-modules/alerting.svg?branch=master)](https://travis-ci.org/cfn-modules/alerting)
[![NPM version](https://img.shields.io/npm/v/@cfn-modules/alerting.svg)](https://www.npmjs.com/package/@cfn-modules/alerting)

# cfn-modules: Alerting

Central SNS topic that receives alerts from other [modules](https://www.npmjs.com/org/cfn-modules) and forwards them to your team via email, HTTP, or HTTPS.

## Install

> Install [Node.js and npm](https://nodejs.org/) first!

```
npm i @cfn-modules/alerting
```

## Usage

```
---
AWSTemplateFormatVersion: '2010-09-09'
Description: 'cfn-modules example'
Resources:
  Alerting:
    Type: 'AWS::CloudFormation::Stack'
    Properties:
      Parameters:
        Email: 'team@org.com' # optional
        HttpEndpoint: 'http://org.com/webhook' # optional
        HttpsEndpoint: 'https://org.com/webhook' # optional
        FallbackEmail: 'user@org.net' # optional
      TemplateURL: './node_modules/@cfn-modules/alerting/module.yml'
```

## marbot

![marbot](https://marbot.io/assets/marbot.png)

Hi, my name is marbot.

I'm a Slack bot supporting your DevOps team to detect and solve incidents on AWS.

I help you to set up AWS monitoring. There are countless possibilities on AWS. Overlooking the important settings is easy. I connect you with all relevant AWS sources. You never miss an incident again.

Don’t get distracted from your deep work, when not absolutely necessary. I do send alerts to a single team member. Of course, I escalate unnoticed alerts to another team member or the whole crew if necessary.

Instead of cluttering up your inbox with emails I do send alerts via Slack. Just re-use your modern team communication solution. Invite me to multiple Slack channels to separate alerts. You can also talk to me.

I add links to AWS Management Console that are relevant to an incident. Contextual links save you time and reduce human error in stressful situations.

[Try marbot for free now!](https://marbot.io/?utm_source=cfn-modules&utm_medium=doc&utm_campaign=alerting)

## Parameters

<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Description</th>
      <th>Default</th>
      <th>Required?</th>
      <th>Allowed values</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Email</td>
      <td>Email address that will receive alerts</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>HttpEndpoint</td>
      <td>HTTP endpoint that will receive alerts via POST requests</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>HttpsEndpoint</td>
      <td>HTTPS endpoint that will receive alerts via POST requests (e.g., a <a href="https://marbot.io/?utm_source=cfn-modules&utm_medium=doc&utm_campaign=alerting">marbot.io endpoint for easy-going incident management</a>)</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>FallbackEmail</td>
      <td>Email address that will receive alerts if alerts can not be delivered</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
  </tbody>
</table>
