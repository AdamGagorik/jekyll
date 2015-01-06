### Jekyll.test

A test website using GitHub pages and jekyll.

## Requirements

###### ruby

1. Check

 ```bash
 ruby --version
 ```

2. Install (if missing)

 ```bash
 sudo apt-get install ruby
 ```

###### bundler

1. Install

 ```bash
 sudo gem install bundler
 ```

###### jekyll

1. Create **Gemfile**

 ```ruby
 source 'https://rubygems.org'
 gem 'github-pages'
 ```

2. Install

 ```bash
 # DO NOT USE SUDO
 bundle install
 ```

3. Update

 ```bash
 bundle update
 ```

## Setup

###### Github Pages

Here are the steps taken for a **project page**.

 1. Create repository on github with whatever name you want.
 2. Create a github-pages branch.

 ```bash
 git checkout -b gh-pages
 ```

 3. Add content and push to the **gh-pages** branch.

Here are the steps for a **user page**.

 1. Create repository on github with the name username.github.io
 2. Add content and push to the **master** branch.

###### Notes

 * **Gemfile** and **Gemfile.lock** should be committed to the **gh-pages** branch.

## Jekyll

There are quite a few ways to get started.

###### Vanilla setup

```bash
# assuming gh-pages is empty
git checkout gh-pages
jekyll new .

# if you have other stuff, like Gemfile or gitignore...
git checkout gh-pages
jekyll new tmp
mv tmp/* .
rmdir tmp/
```

As described in http://jekyllrb.com/docs/github-pages/

Change the config file:

```yaml
baseurl : "/project-name"
```

Change the references to css:
```
{{ site.baseurl }}/path/to/css.css
```

###### Themed

There are quite a few themes online.
You can fork the theme's repository, and change the name (*see above for naming conventions*).
Make your custom changes and push them to your fork.
If the theme maintainer updates the theme, you can merge them into your fork.

You could also just add the theme repository as a remote and pull in its changes.

```bash
# add theme as a remote
git remote add hyde git@github.com:poole/hyde.git
git fetch hyde
git merge hyde/master gh-pages
```

###### Abstracted framework

There are frameworks such as jekyll-bootstrap or octopress that claim to make using jekyll easier.
You can follow their specific instructions.

## Preview Locally

```bash
# start server
bundle exec jekyll serve

# open browser
gnome-www-browser http://0.0.0.0:4000/
```

## View Externally

###### Project-page

```bash
# open browser
gnome-www-browser http://username.github.io/repo-name
```

###### User-page

```bash
# open browser
gnome-www-browser http://username.github.io/
```

## Workflow

```bash
# do work on some branch
git branch newstuff gh-pages
git checkout newstuff

# create or edit some files
echo "Hello!" >> about.html

# add the files an commit
git a about.html
git commit -m "add about page"

# preview the changes
bundle exec jekyll serve
gnome-www-browser http://0.0.0.0:4000/

# merge the changes into the gh-pages branch
git checkout gh-pages
git merge newstuff

# push the changes to github
git push origin gh-pages

# view the changes online
gnome-www-browser http://username.github.io/repo-name
```
