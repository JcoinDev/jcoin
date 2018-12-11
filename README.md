Jcoin Project
================================

https://www.jcoin.co.jp

- Copyright (c) 2009-2014 Bitcoin Developers
- Copyright (c) 2011-2014 Litecoin Developers
- Copyright (c) 2017-2018 Jcoin Developers

What is Jcoin?
----------------

Jcoin is a version of Bitcoin using scrypt as a proof-of-work algorithm.
 - 2.5 minute block targets
 - subsidy halves in 840k blocks (~4 years)
 - ~84 million total coins
 - 50 coins per block
 - 2016 blocks to retarget difficulty

How to Run GUI on Linux?
----------------
Compiler works on Ubuntu 16.0.4.5
http://releases.ubuntu.com/16.04/
First navigate to your Jcoin Source folder $/Desktop/Jcoin/src/
in the terminal of src folder type this command.
 - make -f makefile.unix
 - please wait this can take over 5 mins
 -Now navigate back a folder to the Jcoin directory
 - cd ..
 
in the terminal of jcoin folder type these commands.
 - qmake 
 - make

Now in the Jcoin folder you should see jcoin-qt
in the terminal run this command
 - ls
 - ./jcoin-qt
 - please wait while it connects to the Jcoin network

For more information and help please visit https://www.jcoin.co.jp
------------------------------------------------------------------------------

How to Run GUI on Windows?
----------------
Extract .zip file
 - RUN jcoin-0.8.7.5-win32-setup
 - Allow firewall accesss
 - Read Server and Seed Instructions

------------------------------------------------------------------------------

Seed and Server Instructions
----------------
Windows
 - Search for %appdata% in windows
 - Create jcoin.conf file in %appdata% input addnode ip.
 - addnode=192.168.0.7
 
 Linux
 -$/Home/.jcoin CRTL H to see hidden files
 - create jcoin.conf file in .jcoin input addnode ip.
 - addnode=192.168.0.7
 - connect to server and mine

-----Make Server Seed -----

Create jcoin.conf file inside the file paste code bellow save and run jcoin-qt

- server=1
- rpcuser=user
- password=password

---------------------------

### Dependencies For Linux 16.04 Compiler Build:

sudo apt-get install git
 
sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils
 
sudo apt-get install libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-program-options-dev libboost-test-dev libboost-thread-dev
 
sudo apt-get install libboost-all-dev
 
sudo apt-get install software-properties-common
 
sudo add-apt-repository ppa:bitcoin/bitcoin
 
sudo apt-get update
 
sudo apt-get install libdb4.8-dev libdb4.8++-dev
 
sudo apt-get install libminiupnpc-dev
 
sudo apt-get install libzmq3-dev
 
sudo apt-get install libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler
 
sudo apt-get install libqt4-dev libprotobuf-dev protobuf-compiler


--------------------------------------------------------------------------------------------------------------------------------


License
-------

Jcoin is released under the terms of the MIT license. See `COPYING` for more
information or see http://opensource.org/licenses/MIT. 
Created by Cody Quinn 

Development process
-------------------

Developers work in their own trees, then submit pull requests when they think
their feature or bug fix is ready.

If it is a simple/trivial/non-controversial change, then one of the Jcoin
development team members simply pulls it.

If it is a *more complicated or potentially controversial* change, then the patch
submitter will be asked to start a discussion with the devs and community.

The patch will be accepted if there is broad consensus that it is a good thing.
Developers should expect to rework and resubmit patches if the code doesn't
match the project's coding conventions (see `doc/coding.txt`) or are
controversial.

The `master` branch is regularly built and tested, but is not guaranteed to be
completely stable. [Tags](https://github.com/jcoindev/jcoin/tags) are created
regularly to indicate new official, stable release versions of Jcoin.

Testing
-------

Testing and code review is the bottleneck for development; we get more pull
requests than we can review and test. Please be patient and help out, and
remember this is a security-critical project where any mistake might cost people
lots of money.

### Automated Testing

Developers are strongly encouraged to write unit tests for new code, and to
submit new unit tests for old code.

Unit tests for the core code are in `src/test/`. To compile and run them:

    cd src; make -f makefile.unix test

Unit tests for the GUI code are in `src/qt/test/`. To compile and run them:

    qmake BITCOIN_QT_TEST=1 -o Makefile.test bitcoin-qt.pro
    make -f Makefile.test
    ./jcoin-qt_test

