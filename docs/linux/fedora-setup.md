# Fedora Setup

## OS Setup

- [Add rpmfusion repositories](https://rpmfusion.org/Configuration)
- Update and cleanup
```
sudo dnf update -y
sudo dnf install zlib.i686 ncurses-libs.i686 bzip2-libs.i686 -y
sudo dnf install exfat-utils fuse-exfat -y
sudo dnf install youtube-dl
```
- fedora package cleanup
```
dnf remove package
dnf autoremove
dnf clean all
dnf reinstall
```
## Gnome configuration
```
gsettings set org.gnome.desktop.wm.preferences button-layout ":minimize,maximize,close"

```

## Packages
- [Google Chrome](https://www.google.com/chrome/browser/features.html)
- [Sublime Text](https://www.sublimetext.com/docs/3/linux_repositories.html#dnf)
- [VSCode](https://code.visualstudio.com/docs/setup/linux#_rhel-fedora-and-centos-based-distributions)
- [Docker]()
- [NodeJS](https://nodejs.org/en/download/package-manager/#enterprise-linux-and-fedora)
- [Yarn](https://yarnpkg.com/en/docs/install)
