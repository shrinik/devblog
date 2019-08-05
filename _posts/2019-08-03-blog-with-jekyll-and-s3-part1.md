---
layout: post
title: "Create and Publish a blog using Jekyll & AWS S3 - Part 1"
date: 2019-08-03 19:30:00 -0500
categories: blog, jekyll, GitHub
---

I always wanted to have a blog to document my thoughts and learnings in the field of software engineering. Part 1 documents the steps to create and version control the blog. Part 2 will cover configuring S3 as a static web host and syncing the site to the S3 bucket. 

Jekyll is a static site generator which generates (or builds) a static website which is a collection of HTML, CSS and JavaScript files which you can then serve from a basic web server. If you are a developer then you can understand how your site **actually** works as compared to using a managed WordPress blog where the backend is a black box. Also, Jekyll offers enough scaffolding to start a blog with minimum effort with the option for more customization at a later stage. 

For a web server to serve static files, I went with AWS S3 as S3 buckets can be easily configured to serve as static file hosts and the running costs are very cheap. Also, I had previously obtained a domain name through AWS and configured it using Route53 so I only needed to copy the static files into the bucket to get the blog up and running. Publishing your first post is winning half the battle. I believe ease of use and pride in understanding how everything actually works will help expand it.

## Installing Jekyll

The official tutorial at <https://jekyllrb.com/docs/> is the bet way to install Jekyll. The tutorial at GitHub Pages for installing Jekyll has a high Google rank but personally I found it confusing. You can use any text editor you like to open the site folder and edit the files. I used Visual Studio Code which is my favorite editor (and free in the bargain).

### Open the folder in your text editor and modify the following files:

- (Optional) Update the title, description, url, github*username variables in the _\_config.yml_ file.
- (Optional) Update the content of the _about.md_ file to reflect your blog.
- (Optional) Add a new blog post and remove any existing posts if you like.
- Run the following command in the site directory to build and serve the site on your local machine. It will automatically re-generate the site if you make any changes to the site (hit refresh in your browser to see the new changes). But if you change _\_config.yml_ you will need to stop the server and re-run it.
~~~
bundle exec jekyll serve
~~~

## Versioning the blog

Another advantage of static files is that you can version your blog using using Git (or any other SCM). This allows you to revert your entire blog or specific files to any prior state with the minimum of hassle. Also, committing to the remote repo and ensuring an updated site backup becomes part of your blogging workflow (esepcially when you setup an automated pipeline to build and deploy your blog). 

### To follow the next steps, you will need Git installed and accessible via the shell (command prompt) and a GitHub account.

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

