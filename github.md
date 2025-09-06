# Install the git on the machine
Install using the package
```
sudo apt install git
```
# Update Git Configuration

```
git config --global --unset user.name
git config --global --unset user.email
git config --global user.name "your_username"
git config --global user.email "your_email@example.com"
````
# Configure SSH Key Authentication

```
ssh-keygen -t rsa -b 4096 -C "your.email@xyz.com"

eval "$(ssh-agent -s)"

ssh-add ~/.ssh/id_rsa

cat ~/.ssh/id_rsa.pub
```
# Copy
Add the SSH key to your GitHub account under Settings > SSH and GPG keys.

# Change Remote URL to Use SSH:
Update your repository's remote URL with
```
git remote set-url origin git@github.com:username/repository.git
```