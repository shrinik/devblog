---
layout: post
title: "How to create a blog using Jekyll & AWS S3"
date: 2019-08-03 16:00:00 -0500
categories: jekyll
---

I finally decided to start my developer oriented blog using Jekyll to create a static blog and AWS S3 to host it. Jekyll is a static site generator which is developer friendly and does not need much configuring. I find a lot of setup tends to throw me off from finishing a project.
I already had an AWS account and custom domain that I use for cloud development so S3 was a logical choice to host the blog.

## Install Jekyll

The official tutorial at <https://jekyllrb.com/docs/> is the bet way to install Jekyll. I recommend using Visual Studio Code to modify your newly created site. Open the site folder created in the tutorial using VS Code and do the following:

- Update the title, description, url, github*username variables in the _\_config.yml_ file.
- Update the content of the _about.md_ file to reflect your blog.
- Add a new blog post and remove any existing posts if you like.

Your blog is now ready for hosting.

## Version your blog

An advantage of using Jekyll is that you can version your blog using a tool version control system like Git. This will allow you to revert your blog to any prior state and maintain a remote backup without a dedicated backup routine. You will need Git installed and accessible via the command prompt and also have a GitHub account to follow the next steps in this section.

1. Use the command line and navigate to the site folder and initialize an empty git repository
~~~
git init
~~~
2. Stage the commit and commit the changes
~~~
git add .
git commit -m 'Initial blog version'
~~~
3. Create a remote repository in Github and add the remote locally and push the changes
~~~
git remote blog https://github.com/github_username/reponame.git
git push blog master
~~~    

## Create and configure a new S3 bucket

## Install AWS CLI to sync the site to S3
