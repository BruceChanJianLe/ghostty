# Ghostty

This repository stores notes about using Ghostty on Ubuntu!

## Installation

I use `nix` to build `ghostty` from source and make it available system wide.
The below command uses my ansible script to install `nix` and then build `ghostty`.  
```bash
sudo apt install ansible git -y
ansible-pull -U https://github.com/brucechanjianle/ansible --tags nix, ghostty --ask-become-pass
```

But if you are using Arch Linux! Just install it with `pacman`.  
```bash
sudo pacman -S ghostty
```

## Set Default Terminal

```bash
sudo update-alternatives --install /usr/bin/x-terminal-emulator x-terminal-emulator /usr/local/bin/ghostty 100
```
