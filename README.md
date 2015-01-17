#Installation

-clone and download
- cd to directory
- scons
- sudo scons -prefix=/opt/mongo install

create /data/db 

thats all.
I will write a little more detailed description when I have more time =)
just enjoy!

#Detailed Description

sudo apt-get install build-essential libboost-filesystem-dev libboost-program-options-dev libboost-system-dev libboost-thread-dev scons libboost-all-dev python-pymongo git

git clone https://github.com/sayfullah/MongoPi.git

cd mongo-nonx86/

scons

sudo scons –prefix=/opt/mongo install

Now add mongodb user and set up required directories with correct permissions

sudo adduser --firstuid 100 --ingroup nogroup --shell /etc/false --disabled-password --gecos "" --no-create-home mongodb

sudo mkdir /var/log/mongodb/

sudo chown mongodb:nogroup /var/log/mongodb/

sudo mkdir /var/lib/mongodb

sudo chown mongodb:nogroup /var/lib/mongodb

sudo cp debian/init.d /etc/init.d/mongod

sudo cp debian/mongodb.conf /etc/

sudo ln -s /opt/mongo/bin/mongod /usr/bin/mongod

The config file for mongoDb is: /etc/mongodb.conf

You can start mongoDB by: sudo /etc/init.d/mongod start

You can stop it with: sudo /etc/init.d/mogod stop

You can get the command line by: /opt/mongo/bin/mongo
