# void-redot

This repository contains an XBPS template for packaging the Redot Engine for Void Linux.

It provides `redot` (the editor) and `redot-export-templates`.

Redot is a community-driven fork of the Godot Engine.

## Installation

Clone this repository:

```sh
git clone git@github.com:ihateemoji/void-redot.git
```

Copy the package directory into the `srcpkgs` directory of your Void Packages repository:

```sh
cp -r void-redot/srcpkgs/* /path/to/void-packages/srcpkgs/
```

Build the package:

```sh
./xbps-src pkg redot
```

Install the packages:

```sh
xi redot redot-export-templates
```

## Export templates

After installation, symlink the templates so the editor can find them:

```sh
ln -s /usr/lib/redot/export_templates $HOME/.local/share/redot/export_templates/redot
```

(See `srcpkgs/redot/README.voidlinux` for details.)

## Notes

- Based on the official `godot` template in void-packages, adapted for Redot 26.3.
- Builds the editor and Linux export templates using system libraries where possible.
- May require minor fixes after first build (binary names, musl, etc.).
- Maintainer field in the template is a placeholder — update it before submitting upstream.
