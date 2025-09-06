# Install the git on the machine
Install using the package
```
sudo apt install git
```
# Github settings for push and pull
git config --global --unset user.name
git config --global --unset user.your.email@dot.com
git config --global user.name
git config --global user.name 
git config --global user.email

# For authentication of the key for github 
ssh-keygen -t rsa -b 4096 -C "your.email@xyz.com"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
cat ~/.ssh/id_rsa.pub

# Copy
copy the key and past it into the setting in github account under SSH keys