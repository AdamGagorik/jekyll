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

## Preview Locally

```bash
# start server
bundle exec jekyll serve

# open browser
gnome-www-browser http://0.0.0.0:4000/
```

## Publish

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
