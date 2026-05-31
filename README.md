# Ubuntu
# Building a Blog site from Scratch using Jekyll
Building a website is not as hard or expensive as it was in the past. These days, you do not have to learn a crazy programming lauguage to have your site up and running.
Instead, you can go the Jamstack way. In this article, we go through how to build and deploy a jekyll site.

# Introduction
Jekyl is a Jamstack static website generator. Jamstack is a concept of building website that don't depend on web servers and databases.
Jekyll was released back in 2008 and has been one of the most convenient ways of building all types of sites. It's written in Ruby and uses the Liquid template engine to render web pages.

# Prerequisites
To follow through this tutorial, you will need:
+ A code editor. Feel free to use your prefered code editor. You can download vscode [here](https://go.microsoft.com/fwlink/?LinkID=760868).
+ Some basic skill in HTML and CSS

By the end of this tutorial, you will be able to build a jekyll blog from scratch.
# Step 1- Install Ruby and other prerequisites:

install using apt manager
```
sudo apt-get install ruby-full build-essential zlib1g-dev
```
For linux, you'll need to set up gem installation directory to prevent root permission errors. Add the lines below at the bottom of the .bashrc or .zshrc file located in the home folder.
```
export GEM_HOME="$HOME/gems"
export PATH="$HOME/gems/bin:$PATH"
```
You can use the echo command to append the above lines at the bottom of the .bashrc file.
```
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
```
If your using other shell used according environment
```
echo 'export GEM_HOME="$HOME/gems"' >> ~/.zshrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.zshrc 
```
Then execute file
```
source ~/.bashrc
```
If other shell used that
```
Source ~/.zshrc
```
# Step 2 - Install Jekyll
Jekyll comes as Ruby Gem and can be installed in any system running Ruby. Run the following command below in the terminal to install jekyll
```
gem install jekyll bundler
``

Create a new jekyll site
`` 
jekyll new blog
cd blog
```
See the file structure of the jekyll new blog

We'll look at the file structure. Let's run the site now. Run following command in the terminal.
```
bundle exec jekyll serve
```
The command builds your site and you can access the site at http://127.0.0.1:4000 by default.You can run site using --livereload (-l) flag to autoreload the site after making changes.
```
bundle exec jekyll serve -l
```
If you encounter: `unable to load the EventMachine C extension; to use the pure-ruby reactor, require "em/pure_ruby"',
reinstall the Even Machine.

```
gem uninstall eventmachine
gem install eventmachine --platform ruby
budle exec jekyll serve --livereload
```
If github page unable to develop the website its on from the main file. The do following command give below

# offline build of the site and then load on the site for compression

```
JEKYLL_ENV=production bundle exec jekyll build --trace

JEKYLL_ENV=production bundle exec jekyll build --watch

```

# Jekyll problem for not to run serve then do following commands
1. lsof -wni tcp:4400
Then record the PID
Run 
kill -9 PID

# You’re still hitting the same core issue, but this time the log shows a *different early failure*:

```text
checking for brotli/decode.h... no
checking for brotli/encode.h... no
checking for pkg-config for libbrotlicommon... not found
```

This means the system Brotli development libraries are missing — **but even if you fix this, Ruby 3.3 will still break later (as you already saw).**

So you actually have **two problems**:

---

## ❌ Problem 1: Missing system Brotli dev libraries

Install them:

```bash
sudo apt update
sudo apt install libbrotli-dev pkg-config build-essential ruby-dev
```

This fixes:

* missing `decode.h`
* missing `encode.h`
* missing `pkg-config`

---

## ❌ Problem 2 (the real blocker): Ruby 3.3 incompatibility

You already got this error earlier:

> incompatible pointer type in brotli.c

That means:

👉 `brotli 0.2.3` is **not compatible with Ruby 3.3**

So even after installing `libbrotli-dev`, it will likely FAIL again.

---

# ✅ Real working solutions

## ✔️ Option A (BEST): Remove jekyll-brotli

In your `Gemfile`:

```ruby
# gem "jekyll-brotli"
```

Then:

```bash
bundle install
```

This is the cleanest fix for most Jekyll sites.

---

## ✔️ Option B: Keep compression WITHOUT Ruby gem (recommended alternative)

Install CLI tool:

```bash
sudo apt install brotli
```

After building Jekyll:

```bash
jekyll build
```

Then compress output:

```bash
find _site -type f \( -name "*.html" -o -name "*.css" -o -name "*.js" \) -exec brotli -f -k {} \;
```
---

# 🧠 Bottom line

* Installing `libbrotli-dev` fixes **one missing header issue**
* But **Ruby 3.3 + brotli 0.2.3 is fundamentally incompatible**
* The real fix is to **remove `jekyll-brotli` or avoid Ruby-native Brotli**

---
