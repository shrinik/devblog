---
layout: post
title: "Create and Publish a blog using Jekyll & AWS S3 - Part 1"
date: 2019-08-03 19:30:00 -0500
categories: blog, jekyll, GitHub
---

I always wanted a blog to document my thoughts and learnings in the field of software engineering. Part 1 shows how to create a new blog and version control it. Part 2 will cover configuring S3 as a static web host and building a CodePipeline to automatically build the site and copy the site to S3 whenever you commit a change to GitHub. 

Jekyll is a static site generator which generates a static website, which does not require server-side technologies. A static website comprises of HTML, CSS and JavaScript files. This allows you to understand how your site **actually** works as compared to using a managed WordPress blog where the backend is a black box. Also, Jekyll offers enough scaffolding to start a blog with minimum effort with an option to customize it later. 

I am using an AWS S3 bucket as the web server as it can be configured in under a minute. I had purchased a domain name via AWS and it only took me a minute to point it to the S3 bucket using Route53. So all you have to do is copy the static files built by Jekyll to the bucket to serve your blog to the world. By publishing your blog you have won half the battle. I hope a deeper understanding of just how everything works and the ease of adding new posts will allow you to keep it regularly updated.

**You can find the github repository for this blog at <https://github.com/shrinik/devblog>**

## Installing Jekyll

The official tutorial at <https://jekyllrb.com/docs/> is the bet way to install Jekyll. Use your preferred text editor to open the site folder and edit the files. I use Visual Studio Code which is free.

### Open the folder in your text editor and modify the following files:

- (Optional) Update the title, description, url, github_username variables in the _\_config.yml_ file.
- (Optional) Update the content of the _about.md_ file to reflect your blog.
- (Optional) Add a new blog post and remove any existing posts if you like.
- (Optional) See <https://kramdown.gettalong.org/syntax.html#fenced-code-blocks> on how to use kramdown which is the default Markdown.
- Run the following command in the website directory to build and serve the site on your local machine. This will automatically re-generate the site if you make any changes to the site (refresh your browser to load the changes). Note that if you change anything in _\_config.yml_, you will need to stop the server and re-run the below command.
~~~
bundle exec jekyll serve
~~~

## Versioning your blog

An advantage of a static website is that you can version your blog using using Git (or any other SCM). This allows you to revert your entire blog or specific files to any prior state with the minimum of hassle. Also, committing to the remote repo and ensuring an updated site backup becomes part of your blogging workflow (and will be useful when I show how to setup an automated pipeline to build and deploy your blog in Part 2). <https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository> has good concise explanations on basics of Git.

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