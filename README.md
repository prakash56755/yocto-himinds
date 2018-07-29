Himinds Repo Mainfests for the yocto project Build system

This repository provides repo manifests to setup the yocto build system for rpi target with mender integration.

1. Install Repo.

Download the Repo script:

$ curl https://storage.googleapis.com/git-repo-downloads/repo > repo

Make it executable:

$ chmod a+x repo

Move it on to your system path:

$ sudo mv repo /usr/local/bin/

If it is correctly installed, you should see a Usage message when invoked with the help flag.

$ repo --help

Initialize the repo  client,

$ repo init -u git://github.com/prakash56755/yocto-himinds.git

Once repo is setup,

$ repo sync

Then move to Poky directory,

$ cd poky


