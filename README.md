SCAP Workbench build Debian Trixie
==============

A GUI tool that provides scanning, tailoring and validation functionality for SCAP content

About
-----

SCAP Workbench is a GUI tool that provides scanning, tailoring
and validation functionality for SCAP content. It uses openscap library
to access SCAP functionalities.

Homepage of the source project is https://www.open-scap.org/tools/scap-workbench/

How to run it out of the box
----------------------------

On Debian Trixie:
```console
apt install -y build-essential openssh-client libopenscap-dev libqt5xmlpatterns5-dev ssh-askpass asciidoc cmake pkg-config libpolkit-agent-1-0
```

2) Build SCAP Workbench:
```console
$ mkdir build; cd build
$ cmake ../
```

Then on Debian Trixie if you want test immediately
```console
apt install -y openscap-scanner openscap-utils ssg-base

wget http://ftp.de.debian.org/debian/pool/main/s/scap-security-guide/ssg-debian_0.1.80-1_all.deb
dpkg -i ssg-debian_0.1.80-1_all.deb
rm -rf ssg-debian_0.1.80-1_all.deb

make -j$(nproc) install
```


## Install
Build Debian 13 Trixie de SCAP Workbench 1.2.1.

Cette version est compilée avec :

- Debian 13 Trixie
- Qt 5.15.15
- OpenSCAP 1.4.2
- SCAP Security Guide Debian 13

### Fonctionnalités testées

- Scan SCAP Debian 13
- Profils ANSSI
- Rapports HTML
- Génération de remédiation
- Téléchargement automatique des ressources OVAL Debian

---

### Installation

```bash
wget https://github.com/allpic/scap-workbench-debian13/releases/download/v1.2.1-debian13/scap-workbench_1.2.1+debian13-1_amd64.deb
sudo apt install ./scap-workbench_1.2.1+debian13-1_amd64.deb
```
or
```bash
curl -LO https://github.com/allpic/scap-workbench-debian13/releases/download/v1.2.1-debian13/scap-workbench_1.2.1+debian13-1_amd64.deb
sudo apt install ./scap-workbench_1.2.1+debian13-1_amd64.deb
```

What now?
---------

You should have a built SCAP Workbench executable by now. Please refer to the user manual for documentation on how to use it.

There are 3 ways to get the user manual:

 * Click `Help -> User Manual` in the application
 * Open `/usr/share/doc/scap-workbench/user_manual.html` (installed system-wide) or `doc/user_manual.html` (from the tarball) in your browser
 * Open or download [user manual from the website](https://static.open-scap.org/scap-workbench-1.1/)

How to make a tarball
---------------------
```console
mkdir build; cd build
cmake ../
make package_source
```
