# audacious-bin
https://github.com/audacious-media-player/audacious
https://github.com/audacious-media-player/audacious-plugins

how to run
extract aud.zip
move pkg/bin/{audtool,audacious} to ~/.bin/ or whaatever local path in $PATH
mv  pkg/bin/audtool ~/.bin/
mv  pkg/bin/audacious ~/.bin/
mv pkg/share/icons/hicolor/scalable/apps/audacious.svg ~/.local/share/icons/
mv pkg/share/applications/audacious.desktop ~/.local/share/applications
edit the audacious.desktop to use aud in exec field
move pkg/lib/ to ~/.local/lib/audacious dirs for lib 
mv pkg/lib/ ~/.local/lib/audacious


it wont run without plugins
extract aud-plugins.zip
sudo mv -r build/pkg/usr/local/lib/audacious/ /usr/local/lib/

for winamp skins and localization , you can also put skins in ~/.local/share/audacious/Skins/
sudo mv -r build/pkg/usr/local/share/ /usr/local/lib/


for compressed winamp2 skin wsz install unzip
sudo apt install unzip -y
https://archive.org/details/winampskins
move  skins to ~/.local/share/audacious/Skins/
mv ~/Downloads/*.wsz ~/.local/share/audacious/Skins/

TIP: ctrl+d to make 2x classic winamp skin


gtk only build with least dependecies possible

cat .bin/aud
export export LD_LIBRARY_PATH=$HOME/.local/lib/audacious:$LD_LIBRARY_PATH
audacious "$@"

some plugins need libs like :
audacious/Transport/neon.so  libneon-gnutls.so.27
audacious/Input/wavpack.so   libwavpack.so.1
audacious/Input/opus.so      libopusfile.so.0
non fatal error 
