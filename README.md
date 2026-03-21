# tlp-pd-Debian-trixie
After installing tlp we no longer had power profiles available in desktop GUI.  
This is how to install tlp-pd on Debian trixie to enable power profiles in the GUI

## Breakdown
tlp-pd would not install from standard Debian sources.  
This readme shows how to add the backports repository and install tlp-pd

## Add reposirtory
This is done using deb822 formatting for clarity and security.
First we navigate to /etc/apt/sources.list.d
Avoid editing debian.sources and instead create a new file with the .sources extension such as
debian-backports.sources

Open with your favorite text editor and enter the following:

Types: deb deb-src <br>
URIs: http://deb.debian.org/debian <br>
Suites: trixie-backports <br>
Components: main <br>
Enabled: yes <br>
Signed-By: /usr/share/keyrings/debian-archive-keyring.gpg <br>

## Installing tlp-pd from backports repository

sudo apt -t trixie-backports install tlp tlp-pd tlp-rdw

## Enable tlp-pd

systemctl enable tlp-pd

## Install Complete
tlp-pd power daemon should now be installed and power profiles available in the GUI
