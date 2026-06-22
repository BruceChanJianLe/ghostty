> Looking for help?

<details>
<summary> <h2> Installation </h2> </summary>

If you are on Ubuntu! Simply install it with `snap`.  
```bash
snap install ghostty --classic
```

But if you are using Arch Linux! Just install it with `pacman`.  
```bash
sudo pacman -S ghostty
```

</details>

<details>
<summary> <h2> Set Default Terminal </h2> </summary>

```bash
sudo update-alternatives --install /usr/bin/x-terminal-emulator x-terminal-emulator /usr/local/bin/ghostty 100
```

</details>

<details>
<summary> <h2> SSH Is Different </h2> </summary>

Ghostty intentionally uses `TERM=ghostty` instead of the common `TERM=xterm-256color`.
This is a deliberate design choice by Mitchell Hashimoto — most terminals fake compatibility
by using the `xterm-` prefix, relying on programs doing string matching on `$TERM`, which
is the wrong approach. The correct way is to query the terminfo database directly, and
Ghostty enforces this by having its own terminfo entry.

The downside is that remote machines and pods don't have Ghostty's terminfo entry installed,
so emoji and unicode characters get mangled. The fix is to ship the terminfo entry manually:

```bash
infocmp -x | ssh developer@192.168.XXX.XXX -- tic -x -
```

Or for pods:
```bash
infocmp -x | oc exec -i <pod name> -- tic -x -
```

Or for docker containers:
```bash
infocmp -x | docker exec -i <container> tic -x -
```
</details>
