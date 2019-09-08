# Void lx-brand Image Builder


This is a collection of scripts used for creating an lx-brand Void image.

## Requirements

In order to use these scripts you'll need:

- Alpine, Ubuntu or CentOS running in a VM (required for the `install` script). 
- A SmartOS (or SDC headnode) install (required for the `create-lx-image` script)

Note that the `install` script will fail if run in an lx-brand enironment.

## Usage

1. Run `./install -a <x86_64-musl || x86_64> -x xbps-static-latest.x86_64-musl.tar.xz -d /data/void -m https://alpha.de.repo.voidlinux.org -i void -p "Void Linux" -D "Void 64-bit lx-brand image." -u https://docs.joyent.com/images/container-native-linux` under Void to install Void in a given directory. This will create a tarball of the installation in your working directory (named `<image name>-<YYMMDD>.tar.gz`). See `./install -h` for detailed usage.
2. Copy the tarball to a SmartOS machine or SDC headnode and run `./create-lx-image -t /full/path/to/<image name>-<YYMMDD>.tar.gz` (substituting the name of your tar file). This will create the image file and manifest.
