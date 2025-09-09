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