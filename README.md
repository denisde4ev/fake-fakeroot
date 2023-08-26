# NOTE:!

this repo was created because of termux bug with fakeroot in Arch proot, nowadays seems to be fixed
<br>
<br>
<br>
<br>
<br>

# fake-fakeroot
fake the fakeroot in root

# Installation for Arch/Arch based
1) clone repo and cd:
```
git clone https://github.com/deni2020/fake-fakeroot.git fake-fakeroot && cd fake-fakeroot
```
2) build
* if current fakeroot is not working or missing use:
```
ln -sr fake-fakeroot fakeroot  &&  PATH=$PWD:$PATH makepkg -i
```
* else use just `makepkg -i`

## For just executable use:
```
sudo wget -O /usr/local/bin/fakeroot https://github.com/deni2020/fake-fakeroot/raw/master/fake-fakeroot && \
sudo chmod 755 /usr/local/bin/fakeroot
```
*in /usr/local/bin/ will not be overwritten by pacman*
