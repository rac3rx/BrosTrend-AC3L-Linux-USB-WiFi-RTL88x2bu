#BrosTrend AC3L Linux USB WiFi RTL88x2bu

sudo dnf update && sudo dnf upgrade
sudo dnf install dkms git kernel-devel bc make

# reboot

git clone "https://github.com/RinCat/RTL88x2BU-Linux-Driver.git" /usr/src/rtl88x2bu-git
sed -i 's/PACKAGE_VERSION="@PKGVER@"/PACKAGE_VERSION="git"/g' /usr/src/rtl88x2bu-git/dkms.conf
dkms add -m rtl88x2bu -v git
dkms autoinstall
