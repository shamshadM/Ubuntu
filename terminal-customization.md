## Terminal Customization

Terminal Customization is a way to customize the look and feel of your terminal. It is a great way to make your terminal more user friendly.

## Linux Terminal

Linux Terminal is a terminal emulator for the Linux operating system. It is a powerful terminal emulator that can be used to run commands and programs.

- Default Shell: Bash
- Default Terminal Font: DejaVu Sans Mono

How to Install ZSH
```
sudo apt install zsh
```
**Note:** if it ask you yes type `y`

Change default shell
By default it was set on `bash` shell. Check by

```
echo $0
```

It will return `bash`. Now type & enter the root password.
```
chsh
```
After seeing Changing the new shell for `username`. Enter the new value, or press ENTER for default
```
Login Shell [/bin/bash]:/bin/zsh
```
Now do reboot your system manually or from command line

```
sudo reboot
```
This time it will return `zsh`.

Install Oh My Zsh
The below command will work if your system have already installed this package.

- Curl
- Git
- Zsh

```
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
If curl is not installed, then you can install it by

```
sudo apt install curl
```

If git is not installed, then you can install it by

```
sudo apt install git
```

If zsh is not installed, then you can install it by

```
sudo apt install zsh
```

After successful installation, you will see the following message

```
Oh My Zsh! is now installed.
```

Theme of Oh My Zsh
You can change the theme of Oh My Zsh by

```
cd ~/.oh-my-zsh/themes
```
### zsh default themes website
check following website for the themes
[Themes]
(https://github.com/ohmyzsh/ohmyzsh/wiki/Themes)

Edit the theme accordingly for your choice

```
vim ~/.zshrc
```

ZSH_THEME="jonathan"

## Install Plugin according to your need
I have install following plugin
- autosuggestions
- syntax-highlighting
I used following command to install the plugin
```
git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions`
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
```
### Edit ~/.zshrc file
```
vim ~/.zshrc 
````
to include plugins
plugins=(git zsh-autosuggestions zsh-syntax-highlighting history)

### The plugins include with ohmyzsh check the link below
https://github.com/ohmyzsh/ohmyzsh/wiki/Plugins


##### Nerd Font
https://www.nerdfonts.com/


You can see on line 11 or other line a text like this

```
ZSH_THEME="robbyrussell"
```

Change the value to `powerlevel10k/powerlevel10k`

```
ZSH_THEME="powerlevel10k/powerlevel10k"
```

Now restart your terminal.

I have used the following theme Powerlevel10K
```
git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
```
```
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

Change font of the terminal
To change the font if your system has already installed font manager, then you can change the font easily.

Download the font
Open the font and install it
Change font in linux terminal
Preferences -> Profile (Unnamed/Anything) -> Text -> Text Appearance -> Check the box "Custom font"
Click on the font name and select the `MesloLGS NF` font.
Change the font size to `10` or any other size.
Click Select.
Exit the terminal and open it again.

If you don't want or don't have installed font manager, then you can install
Donwload the fonts
Open the folder and select all the fonts Ctrl+H
Now all the hidden files will be shown.

Click Ctrl+Shift+N & named the folder .fonts
Enter the directory & paste all the fonts
Go back to the Home directory & again click Ctrl+H

Now if your system have to be installed Gnome Tweak Tool, if it is installed then open the terminal & type

```
sudo apt install gnome-tweaks
```

Customize the Powerlevel10K theme
Now you can customize the theme by editing the file `.zshrc`
From the root directory of your system, open the file `.zshrc` by


- Does this look like a diamond (rotated square)
  y
- Does this look like a lock
  y
- Does this look like a Debian logo (swirl/spiral)
  y
- Does all these icons fit between the crosses?
  y
- Prompt Style
  recommended 3 (Rainbow)
- Character Set
  recommended 1 (Unicode)
- Show current time
  recommended 1 (No)
- Prompt Separator
  recommended 1 (Angled)
- Prompt Heads
  recommended 1 (Sharp)
- Prompt Tails
  recommended 1 (Flat)
- Prompt Height
  recommended 1 (One Line)
- Prompt Connection
  recommended 1 (Disconnected)
- Prompt Frame
  recommended 1 (No Frame)
- Prompt Spacing
  recommended 2 (Sparse)
- Icons
  recommended 2 (Many Icons)
- Prompt Flow
  recommended 1 (Concise)
- Enable Transient Prompt
  recommended n (No)
- Instant Prompt Mode
  recommended 1 (Verbose)
- Apply Changes to ~/.zshrc
  y

Customize the Powerlevel10K theme

```
p10k configure
```

Restart your terminal.

```
exec zsh
```

https://ohmyz.sh/
https://github.com/romkatv/powerlevel10k

To show username on terminal
Go to root directory
Open the ~/.p10k.zsh file by

```
vim ~/.p10k.zsh gedit ~/.p10k.zsh
```

Press Ctrl+F & type

```
typeset -g POWERLEVEL9K_CONTEXT_{DEFAULT,SUDO}_{CONTENT,VISUAL_IDENTIFIER}_EXPANSION=
```

You will able to see

```
# Don't show context unless running with privileges or in SSH.
# Tip: Remove the next line to always show context.
typeset -g POWERLEVEL9K_CONTEXT_{DEFAULT,SUDO}_{CONTENT,VISUAL_IDENTIFIER}_EXPANSION=
```

Changes to

```
# Don't show context unless running with privileges or in SSH.
# Tip: Remove the next line to always show context.
# typeset -g POWERLEVEL9K_CONTEXT_{DEFAULT,SUDO}_{CONTENT,VISUAL_IDENTIFIER}_EXPANSION=
```

Press Ctrl+S. Exit the file.
Now restart the terminal.
You can see the username on the top right corner.
