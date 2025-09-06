# Github settings for push and pull
git config --global --unset user.name
git config --global --unset user.shamshadM
git config --global --unset user.shamshd.rattan@gmail.com
git config --global user.name
git config --global user.name "shamshadM"
git config --global user.email "shamshad.rattan@gmail.com"

# For authentication of the key for github 
ssh-keygen -t rsa -b 4096 -C "shamshad.rattan@gmail.com"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
ssh-keygen -t rsa -b 4096 -C "shamshad.rattan@gmail.com"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
cat ~/.ssh/id_rsa.pub

# Copy
copy the key and past it into the setting and SSH keys