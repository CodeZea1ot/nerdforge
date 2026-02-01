# Nerd Forge

A tool for nerds to manage their Nerd Fonts

![Nerd Forge Logo](/assets/images/nerdforge.png)

**Nerd Forge** is a command-line tool to install, delete, check, and manage Nerd Fonts on Linux. It supports both `.tar.xz` and `.zip` releases from [the official Nerd Fonts GitHub repository](https://github.com/ryanoasis/nerd-fonts) and automatically rebuilds your font cache after operations.

It's so easy, even a nerd could use it.

## Features

- Easily manage your Nerd Fonts with one-liners like
  - `nerdforge install <FontName>`
- Downloads the font's `.tar.xz` or falls back to `.zip` automatically
- Delete installed Nerd fonts
- Check if a Nerd Font is installed
- List all installed Nerd Fonts
- Diagnose system dependencies with `doctor`

---

## Installation

### Dependencies

#### Download Tool

You only need one of these installed. **Nerd Forge** will prefer `curl` but use `wget` if that is all you have.

```sh
curl --version
wget --version # Fall back if curl not found
```

#### Extraction Tool

```sh
tar --version
unzip -v # Fall back if tar not found
```

The following tool should already be installed on your system by default, but it never hurts to check:

```sh
fc-cache --version
```

### Downloading a Release

Simply head over to [Releases](https://github.com/CodeZea1ot/nerdforge/releases), download the `nerdforge` asset for your desired version, and then put it in your `$PATH`. I recommend `/usr/local/bin`.

```bash
sudo cp /path/to/nerdforge /usr/local/bin/nerdforge
```

### Cloning the Repo

You can also install `nerdforge` by cloning this repo and then creating a symbolic link that is available within your `$PATH`.

This installation method allows you to simply `git pull` this repo whenever you want the latest version from the `main` branch.

It also allows you to swap the version of `nerdforge` you are using by changing git branches, which is useful for exploring features currently in development but not yet in a release.

```bash
git clone git@github.com:CodeZea1ot/nerdforge.git
cd nerdforge
sudo ln -s $(pwd)/nerdforge /usr/local/bin/nerdforge
```

---

## Uninstallation

To uninstall, simply `rm` the symbolic link or copied binary you created during installation. If you put it in `/usr/local/bin` you could just do the following.

```bash
sudo rm /usr/local/bin/nerdforge
```

---

## Usage

```
Usage:  nerdforge [option]
        nerdforge <command> [args]

Examples:
  nerdforge install JetBrainsMono
  nerdforge delete Hack
  nerdforge check FiraCode
  nerdforge list
  nerdforge --version
  nerdforge -h

```

### Options

| Option            | Description            |
| ----------------- | ---------------------- |
| `-v`, `--version` | Show nerdforge version |
| `-h`, `--help`    | Show help message      |

### Commands

| Command              | Description                       |
| -------------------- | --------------------------------- |
| `install <FontName>` | Install a Nerd Font               |
| `delete <FontName>`  | Delete a Nerd Font                |
| `check <FontName>`   | Check if a Nerd Font is installed |
| `list`               | List installed Nerd Fonts         |
| `doctor`             | Check system dependencies         |
| `version`            | Show nerdforge version            |
| `help`               | Show this help message            |

### Arguments

| Argument    | Description                              |
| ----------- | ---------------------------------------- |
| `FontName ` | Name of the Nerd Font, ex. `IBMPlexMono` |

---

## Notes

The `<FontName>` argument is simply the filename of the font asset you want to download from [the latest release of Nerd Fonts](https://github.com/ryanoasis/nerd-fonts/releases/latest/)

## License

**Nerd Forge** is released under the [MIT License](LICENSE).

**External Dependencies:**

**Nerd Forge** does not distribute Nerd Fonts. It is simply a tool for interfacing with [the official Nerd Fonts GitHub repository](https://github.com/ryanoasis/nerd-fonts)
