---
layout: post
title: "How to setup up an AWS CodePipeline"
date: 2019-08-17 19:30:00 -0500
categories: AWS, CodePipeline, CodeBuild, S3
---

Complex technical tasks do not always work the first time around and debugging them is hard due to the number of unknowns. It is faster and easier to simplify the tasks and get them working first. This post discusses how to setup a simple AWS CodePipeline using GitHub, AWS CodePipeline, AWS CodeBuild and AWS S3. This can be used as a template for more complex continuous delivery pipelines.

 The pipeline will be triggered when code is pushed to a remote GitHub repository containing source code for the Hello World program in C. It will use the source code to compile an executable file which will be deployed to an S3 bucket.


**You can find the github repository used in this post at <https://github.com/shrinik/aws-pipeline-test>**

## Prerequisites - GitHub Repository and S3 bucket
* Fork my repository from the above link
* Create a new S3 bucket with the default options (should be in the same region where you will create the CodePipeline)

## Create a CodePipeline





