---
title: Installation
---

# Client

You can download the client from [GitHub](https://github.com/Tensamin/Frontend/releases) or directly from the [Homepage](https://tensamin.net).
For linux we have `.deb` and `.rpm` files on github, two AUR packages and a Nix Flake.

### Arch Linux

This includes [these distros](https://wiki.archlinux.org/title/Arch-based_distributions)

##### Easy Install

- `paru -S tensamin-bin`
- `paru -S tensamin-git`

##### Manual Install

```sh
git clone https://aur.archlinux.org/tensamin-bin
cd tensamin-bin
makepkg -si
```

```sh
git clone https://aur.archlinux.org/tensamin-git
cd tensamin-git
makepkg -si
```

### Nix Flake

**flake.nix**
```nix
{
  # ...
  inputs = {
    tensamin.url = "github:Tensamin/Frontend";
    # ...
  };

  outputs = {
    tensamin,
    # ...
  }:
  # ...
}
```

**configuration.nix**
```nix
{ }: {
  # ...
  environment.systemPackages = [
    inputs.tensamin.packages.${pkgs.system}.default
  ];
  # ...
}
```

# Iota
### The Iota can be installed using the following methods:

### GitHub

```bash
git clone github.com/Tensamin/Iota
cd Iota
cargo build --release
sudo cp target/release /lib/iota -fr
sudo ln /lib/iota /usr/bin/iota
```

### Docker

Not available yet!

```yaml
services:
```

`docker run /`

### Nix Flake

Not available yet!

```nix
services.iota = {
  enable = true;
  id = "<uuid>";
  users = [
    "<uuid>"
  ];
};
```
