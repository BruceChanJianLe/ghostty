# Ghostty

This repository stores notes about using Ghostty on Ubuntu!

## Installation

I use nix to install my ghostty and make it available system wide.

```bash
sudo apt install ansible git -y
ansible-pull -U https://github.com/brucechanjianle/ansible --tags nix, ghostty --ask-become-pass
```

## Set Default Terminal

```bash
sudo update-alternatives --install /usr/bin/x-terminal-emulator x-terminal-emulator /usr/local/bin/ghostty 100
```
