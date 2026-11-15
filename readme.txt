the python script is used to control the screen if using volumio.

volumio commands used https://developers.volumio.com/api/command-line-client

To make it possible to enable/disable the screen enter the following commands:

   export DISPLAY=:0
   xset q
   xset dpms force off       // turn screen off
   xset dpms force on        // turn screen on


how to install:

python3 -- version      // check python
cd /home/volumio        // go to directory where we will put the code
git clone  (deze repro) // clone the software
pwd                     // verify you are in /home/volumio/volumioscreen
sudo apt update         // update
sudo ap install python3-venv python3-full  // installeer virtual environment
python3 -m venv ./venv  //maak virtual environment
source venv/bin/activate // activeer virtual environment
python -m pip install --upgrade pip // upgrade pip
which python             // check python
pip install RPi.GPIO     // install rpi.gpio, nodig voor script
sudo cp autoScreen.service /lib/systemd/system // copieer setup naar autostart
sudo systemctl enable autoScreen // maak script bekend
sudo systemctl start autoScreen  // start script

handige commandos:
sudo systemctl status autoScreen
journalctl -u autoScreen
source ./venv/bin/actiate 

commands to do 
py --list     shows intalls versions of pyton
py -3.7 -m venv .venv maakt een venv met python 3.7
sudo python3 -m venv --system-site-packages /usr/.env  // moet tegenwoordig
. .venv/bin/activate     // sourced!!!
pip install RPi.GPIO

versie die we gaan gebruiken is 3


copieer autoScreen.service naar /lib/systemd/system
cmd: sudo cp autoScreen.service /lib/systemd/system

activeren service commandos
cmd: sudo systemctl enable autoScreen
cmd: sudo systemctl start autoScreen

status checken:
cmd: sudo systemctl status autoScreen:
log: journalctl -u autoScreen
