Electrum-DOGED - lightweight DogecoinDark client for the DOGED i2p electrum server
------------------------------------------------
![Electrum-DOGED](https://raw.githubusercontent.com/doged/electrum-doged-i2p/master/electrumlogo.png)

Licence: GNU GPL v3

Authors: sunerok, bitspill & whit3water

Language: Python

Homepage: http://electrum-doged.space/


1.a) GETTING STARTED WITH UBUNTU/LINUX
------------------
* first, we install i2p.

sudo apt-add-repository ppa:i2p-maintainers/i2p

sudo apt-get update

sudo apt-get install i2p

cd ~

cd .i2p

sudo nano i2ptunnel.config

* (now paste the following at the end of the file)

tunnel.7.name=dogedsock9000

tunnel.7.option.i2cp.closeIdleTime=1800000

tunnel.7.option.i2cp.closeOnIdle=false

tunnel.7.option.i2cp.delayOpen=false

tunnel.7.option.i2cp.destination.sigType=0

tunnel.7.option.i2cp.newDestOnResume=false

tunnel.7.option.i2cp.reduceIdleTime=1200000

tunnel.7.option.i2cp.reduceOnIdle=false

tunnel.7.option.i2cp.reduceQuantity=1

tunnel.7.option.i2p.streaming.connectDelay=0

tunnel.7.option.i2ptunnel.httpclient.allowInternalSSL=false

tunnel.7.option.i2ptunnel.httpclient.sendAccept=false

tunnel.7.option.i2ptunnel.httpclient.sendReferer=false

tunnel.7.option.i2ptunnel.httpclient.sendUserAgent=false

tunnel.7.option.i2ptunnel.useLocalOutproxy=true

tunnel.7.option.inbound.backupQuantity=0

tunnel.7.option.inbound.length=3

tunnel.7.option.inbound.lengthVariance=0

tunnel.7.option.inbound.nickname=doged

tunnel.7.option.inbound.quantity=2

tunnel.7.option.outbound.backupQuantity=0

tunnel.7.option.outbound.length=3

tunnel.7.option.outbound.lengthVariance=0

tunnel.7.option.outbound.nickname=doged

tunnel.7.option.outbound.quantity=2

tunnel.7.option.outproxyAuth=false

tunnel.7.option.persistentClientKey=false

tunnel.7.option.useSSL=false

tunnel.7.privKeyFile=i2ptunnel7-privKeys.dat

tunnel.7.sharedClient=false

tunnel.7.startOnLoad=true

tunnel.7.type=sockstunnel

* now save the file (ctrl-x and yes)

i2prouter restart

* now we install the i2p electrum client:

sudo apt-get install git pyqt4-dev-tools python-pip python-dev python-slowaes

sudo pip install pyasn1 pyasn1-modules pbkdf2 tlslite qrcode

git clone https://github.com/doged/electrum-doged-i2p && cd electrum-doged-i2p

pyrcc4 icons.qrc -o gui/qt/icons_rc.py

sudo python setup.py install

To run Electrum from this directory, just do:
---------------------------------------------
  ./electrum-doged


To update your copy of the electrum client:
-------------------------------------------
cd electrum-doged-i2p

git pull

sudo python setup.py install

1.b) GETTING STARTED WITH WINDOWS
------------------

* download this repo as a zip and extract it to where you would like it to run from. 
https://github.com/doged/electrum-doged-i2p/archive/master.zip

* download i2p for windows here: https://geti2p.net/en/download/0.9.20/clearnet/https/download.i2p2.de/i2pinstall_0.9.20_windows.exe/download

now go to C:\program files\i2p\ and edit i2ptunnel.config

* add the following lines to the end of the file:

tunnel.7.name=dogedsock9000

tunnel.7.option.i2cp.closeIdleTime=1800000

tunnel.7.option.i2cp.closeOnIdle=false

tunnel.7.option.i2cp.delayOpen=false

tunnel.7.option.i2cp.destination.sigType=0

tunnel.7.option.i2cp.newDestOnResume=false

tunnel.7.option.i2cp.reduceIdleTime=1200000

tunnel.7.option.i2cp.reduceOnIdle=false

tunnel.7.option.i2cp.reduceQuantity=1

tunnel.7.option.i2p.streaming.connectDelay=0

tunnel.7.option.i2ptunnel.httpclient.allowInternalSSL=false

tunnel.7.option.i2ptunnel.httpclient.sendAccept=false

tunnel.7.option.i2ptunnel.httpclient.sendReferer=false

tunnel.7.option.i2ptunnel.httpclient.sendUserAgent=false

tunnel.7.option.i2ptunnel.useLocalOutproxy=true

tunnel.7.option.inbound.backupQuantity=0

tunnel.7.option.inbound.length=3

tunnel.7.option.inbound.lengthVariance=0

tunnel.7.option.inbound.nickname=doged

tunnel.7.option.inbound.quantity=2

tunnel.7.option.outbound.backupQuantity=0

tunnel.7.option.outbound.length=3

tunnel.7.option.outbound.lengthVariance=0

tunnel.7.option.outbound.nickname=doged

tunnel.7.option.outbound.quantity=2

tunnel.7.option.outproxyAuth=false

tunnel.7.option.persistentClientKey=false

tunnel.7.option.useSSL=false

tunnel.7.privKeyFile=i2ptunnel7-privKeys.dat

tunnel.7.sharedClient=false

tunnel.7.startOnLoad=true

tunnel.7.type=sockstunnel

* save the file and go to start menu, and click i2p (no window)

* download python 2.7 for windows here: https://www.python.org/ftp/python/2.7.10/python-2.7.10.msi

* download Microsoft Visual C++ Compiler for Python 2.7 here: http://www.microsoft.com/en-us/download/confirmation.aspx?id=44266

* download python qt4: http://sourceforge.net/projects/pyqt/files/PyQt4/PyQt-4.11.3/PyQt4-4.11.3-gpl-Py2.7-Qt4.8.6-x64.exe

* then open start folder, type "cmd" and hit enter. 
 
* then, in command prompt, go into the directory where you unzipped electrum-dogedi2p-master:

pyrcc4 icons.qrc -o gui/qt/icons_rc.py

py -m pip install pip pyasn1 pyasn1-modules pbkdf2 tlslite qrcode ecdsa ltc_scrypt

py setup.py install


1.c) GETTING STARTED WITH MAC OSX
------------------

install python if you dont already have it.

https://www.python.org/ftp/python/2.7.10/python-2.7.10-macosx10.6.pkg

pip install slowaes

python setup.py build

Modify electrum-doged and change python2 to python in the first line

sudo python setup.py install

then modify the i2ptunnel.config file in the i2p directory and add the following to the end of it:

tunnel.7.name=dogedsock9000

tunnel.7.option.i2cp.closeIdleTime=1800000

tunnel.7.option.i2cp.closeOnIdle=false

tunnel.7.option.i2cp.delayOpen=false

tunnel.7.option.i2cp.destination.sigType=0

tunnel.7.option.i2cp.newDestOnResume=false

tunnel.7.option.i2cp.reduceIdleTime=1200000

tunnel.7.option.i2cp.reduceOnIdle=false

tunnel.7.option.i2cp.reduceQuantity=1

tunnel.7.option.i2p.streaming.connectDelay=0

tunnel.7.option.i2ptunnel.httpclient.allowInternalSSL=false

tunnel.7.option.i2ptunnel.httpclient.sendAccept=false

tunnel.7.option.i2ptunnel.httpclient.sendReferer=false

tunnel.7.option.i2ptunnel.httpclient.sendUserAgent=false

tunnel.7.option.i2ptunnel.useLocalOutproxy=true

tunnel.7.option.inbound.backupQuantity=0

tunnel.7.option.inbound.length=3

tunnel.7.option.inbound.lengthVariance=0

tunnel.7.option.inbound.nickname=doged

tunnel.7.option.inbound.quantity=2

tunnel.7.option.outbound.backupQuantity=0

tunnel.7.option.outbound.length=3

tunnel.7.option.outbound.lengthVariance=0

tunnel.7.option.outbound.nickname=doged

tunnel.7.option.outbound.quantity=2

tunnel.7.option.outproxyAuth=false

tunnel.7.option.persistentClientKey=false

tunnel.7.option.useSSL=false

tunnel.7.privKeyFile=i2ptunnel7-privKeys.dat

tunnel.7.sharedClient=false

tunnel.7.startOnLoad=true

tunnel.7.type=sockstunnel

then restart i2p, and 

python electrum-doged

2. HOW OFFICIAL PACKAGES ARE CREATED
------------------------------------

python mki18n.py

pyrcc4 icons.qrc -o gui/qt/icons_rc.py

python setup.py sdist --format=zip,gztar

On Mac OS X:

  # On port based installs
  
  sudo python setup-release.py py2app

  # On brew installs
  
  ARCHFLAGS="-arch i386 -arch x86_64" sudo python setup-release.py py2app --includes sip

  sudo hdiutil create -fs HFS+ -volname "Electrum-DOGED" -srcfolder dist/Electrum-DOGED.app dist/electrum-doged-VERSION-macosx.dmg


[![Visit our i2p IRC Chat!] 
127.0.0.1 6668 #dogecoindark
