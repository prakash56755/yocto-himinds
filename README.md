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

Run the script to setup the initial environment and build setup,

$ ./env-setup.sh build-test

Running the above command will start to build the BSP.

Once the build is completed, you need to flash the image in SD.

$ cd poky/build-test/tmp/deploy/images/raspberrypi3 

$ sudo dd if=himinds-basic-image-raspberrypi3.sdimg of=/dev/sdb bs=1M && sudo sync

Here sdb is the device node of connected SD in host PC.



Note: if you face below error on initializing the repo,

error.GitError: --force-sync not enabled; cannot overwrite a local work tree. If you're comfortable with the possibility of losing the work tree's git metadata, use `repo sync --force-sync poky/` to proceed.

$ repo sync --force-sync
