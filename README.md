# Ghostty

This repository stores notes about using Ghostty on Ubuntu!

<details>

<summary> ## Installation </summary>

If you are on Ubuntu! Simply install it with `snap`.  
```bash
snap install ghostty --classic
```

But if you are using Arch Linux! Just install it with `pacman`.  
```bash
sudo pacman -S ghostty
```

</details>

## Set Default Terminal

```bash
sudo update-alternatives --install /usr/bin/x-terminal-emulator x-terminal-emulator /usr/local/bin/ghostty 100
```
