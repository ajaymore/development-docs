# Fedora Setup

## OS Setup

- [Add rpmfusion repositories](https://rpmfusion.org/Configuration)
- Update and cleanup
```
sudo dnf update -y
sudo dnf install zlib.i686 ncurses-libs.i686 bzip2-libs.i686 -y
sudo dnf install exfat-utils fuse-exfat -y
```
- fedora package cleanup
```
dnf remove package
dnf autoremove
dnf clean all
dnf reinstall
```
