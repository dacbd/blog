---
title: 'Zero to Prod - GKE'
date: 2024-10-07T21:07:42+09:00
# weight: 1
tags: ["first"]
author: "Daniel Barnes"
showToc: true
TocOpen: false
draft: true
hidemeta: false
comments: false
description: "Go from nothing to a comprehenive production style deployment."
canonicalURL: "https://canonical.url/to/page"
disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: false
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
editPost:
    URL: "https://github.com/dacbd/blog/content"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---

# Intro

Our goal is to go from nothing to __Production__ ready deployment in GCP (from the perpective of a small team, a single DevOps member, or your side-project that will totally get some traffic).

First off I'm going to use this "production ready" term a little loosely, I think everyone has there own definition of what that means.
We aren't going in-depth on every detail and depending on your risk tolerance/security posture there may be many more things you should do to be "production ready".

All that said I'm confindent this will get you at least %90 there if not all the way.

I love automation, and things the "just work" so, I have two __meta goals__ of our setup.

First, as the title says we are going to go from nothing to deployment, but with the least amount of click ops possible.
A sub goal of this is, consistent repeatabilty, meaning if something goes wrong we could delete our whole project and start from scratch.
With a few commands we can be back up and running.

Second, our setup should be as hands off as possible, set it and forget it.
This is going to inform some of our technology choices, but we arent going full __serverless__ but we don't want to worry patching servers, or configuring HAProxy.
At the same time we want something, where if a Experienced DevOps Engineer joined the project, no eyebrows would be raised and they could take over responsibilty easily.


We are going cover:
- basic static infra
- vpc networking
- kubernetes
- dns
- loadbalancing
- logging
- metrics
- and basic security along the way.

# Getting Started



# Terraform

In the git repo you can see the whole teraform setup together.
As we progress I will show the relevant parts as they come up.

## Private Network

## k8s Cluster

## LoadBalancer

## Logging

logging is pretty simple with our GKE setup, we don't need to do much.
No need to setup fluentd, GCP **automagicly** collects our container logs for us.
We will setup a seperate logging bucket and setup the logging sink.
After that is complete you can just used GCP Log explorer to inspect your logs.

## Metrics

## Misc. Notes on security.







terraform basic network
- essential static infra
    - vpc
- GKE definition
- static ingress elements
    - static IP
    - ssl policy
    - dns authorization
- dns? 

namecheap / external dns
- CNAME acme challenge
- A record to static IP

dns authorization
- https://cloud.google.com/certificate-manager/docs/dns-authorizations


kubernetes setup
- GKE autopilot
load balancer / ingress config / ssl policy
- https://cloud.google.com/kubernetes-engine/docs/how-to/ingress-configuration#create_ingress
- health checks



