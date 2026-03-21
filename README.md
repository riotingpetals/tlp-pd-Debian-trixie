# tlp-pd-Debian-trixie
After installing tlp we no longer had power profiles available in desktop GUI. <br>
This is how to install tlp-pd on Debian trixie to enable power profiles in the GUI <br>

## Breakdown
tlp-pd would not install from standard Debian sources. <br>
This readme shows how to add the backports repository and install tlp-pd <br>

## Add reposirtory
This is done using deb822 formatting for clarity and security. <br>
First we navigate to `/etc/apt/sources.list.d` <br>
Avoid editing debian.sources and instead create a new file with the .sources extension such as
debian-backports.sources

Open with your favorite text editor and enter the following:
```
Types: deb deb-src 
URIs: http://deb.debian.org/debian 
Suites: trixie-backports 
Components: main 
Enabled: yes 
Signed-By: /usr/share/keyrings/debian-archive-keyring.gpg
```
## Installing tlp-pd from backports repository

`sudo apt -t trixie-backports install tlp tlp-pd tlp-rdw`

## Enable tlp-pd

`systemctl enable tlp-pd`

## Install Complete
tlp-pd power daemon should now be installed and power profiles available in the GUI
