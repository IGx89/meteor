# Meteor

Meteor is an ultra-simple environment for building modern web
applications.

With Meteor you write apps:

* in pure Javascript
* that send data over the wire, rather than HTML
* using your choice of popular open-source libraries

Documentation is available at http://docs.meteor.com/

## Installing on a Raspberry Pi device

Download the Raspbian Wheezy armhf Raspberry Pi minimal image and put it on a 1+ GB SD card: http://www.linuxsystems.it/raspbian-wheezy-armhf-raspberry-pi-minimal-image/

Start up the OS on the device using the SD card you built

Install packages required by fibers and Meteor:
	
    apt-get update
	apt-get install python make g++ curl

Install Meteor:

	mkdir /opt/meteor
	cd /opt
	git clone https://github.com/IGx89/meteor.git
	cd meteor/scripts
	./generate-dev-bundle.sh
	cd ..
	./meteor

To add Meteor to your PATH, run `nano /etc/profile` and then put the following right before the `export PATH` line:

    # add Meteor to path
    PATH="$PATH:/opt/meteor"

Log out of the terminal session and go back in, to make the PATH change take effect

Setup mongodb (change to address of a mongo database running on a different computer -- doesn't support running locally yet):

	export MONGO_URL=mongodb://192.168.1.108:27017/todos

Create and run a Meteor app:

	mkdir ~/apps
	cd apps
	meteor create --example todos
	cd todos
	meteor

## Todo

* Implement support for running mongodb locally

## Developer Resources

Building an application with Meteor?

* Announcement list: sign up at http://www.meteor.com/
* Ask a question: http://stackoverflow.com/questions/tagged/meteor
* Meteor help and discussion mailing list: https://groups.google.com/group/meteor-talk
* IRC: `#meteor` on `irc.freenode.net`

Interested in contributing to Meteor?

* Core framework design mailing list: https://groups.google.com/group/meteor-core
* Contribution guidelines: https://github.com/meteor/meteor/tree/devel/Contributing.md
