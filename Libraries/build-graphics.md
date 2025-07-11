# Building graphics

```bash
sudo apt install liblcms2-dev libcairo2-dev libjpeg8-dev libpng-dev libtiff5-dev
git clone https://github.com/gnustep/libs-opal
cd libs-opal
make
sudo -E make install
cd ..
git clone https://github.com/gnustep/libs-quartzcore
cd libs-quartzcore
make
sudo -E make install
```