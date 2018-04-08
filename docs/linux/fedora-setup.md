# Fedora Setup

## OS Setup

- [Add rpmfusion repositories](https://rpmfusion.org/Configuration)
- Update and cleanup
```
sudo dnf update -y
sudo dnf install zlib.i686 ncurses-libs.i686 bzip2-libs.i686 -y
sudo dnf install exfat-utils fuse-exfat font-manager cabextract -y
sudo dnf install youtube-dl -y
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
```
wget https://github.com/kakkoyun/linux.files/raw/master/fonts/Consolas.ttf
{
  "editor.formatOnSave": true,
  "window.zoomLevel": 0,
  "editor.fontFamily": "CONSOLAS",
  "workbench.colorTheme": "Kary － Light",
  "prettier.eslintIntegration": true,
  "prettier.singleQuote": true
}
```
- [Docker](https://docs.docker.com/install/linux/docker-ce/fedora/#set-up-the-repository)
- [NodeJS](https://nodejs.org/en/download/package-manager/#enterprise-linux-and-fedora)
```
[File Watching](https://code.visualstudio.com/docs/setup/linux#_visual-studio-code-is-unable-to-watch-for-file-changes-in-this-large-workspace-error-enospc)
```
- [Yarn](https://yarnpkg.com/en/docs/install)
