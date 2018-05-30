 Repo Manifests for the Yocto Project Build System
=============================================
This repository provides Repo manifests to setup the Yocto build system for 
supported Gumstix products.

The Yocto Project allows the creation of custom linux distributions for embedded
systems, including Gumstix-based systems.  It is a collection of git
repositories known as *layers* each of which provides *recipes* to build
software packages as well as configuration information.

Repo is a tool that enables the management of many git repositories given a 
single *manifest* file.  Tell repo to fetch a manifest from this repository and
it will fetch the git repositories specified in the manifest and, by doing so,
setup a Yocto Project build environment for you!

Getting Started
---------------
**1.  Install Repo.**

Download the Repo script:

    $ curl http://commondatastorage.googleapis.com/git-repo-downloads/repo > repo

Make it executable:

    $ chmod a+x repo

Move it on to your system path:

    $ sudo mv repo /usr/local/bin/

If it is correctly installed, you should see a Usage message when invoked
with the help flag.

    $ repo --help

**2.  Initialize a Repo client.**

Create an empty directory to hold your working files:

To test out the bleeding edge, type:

    $ repo init -u git://github.com/hiiaka/yocto-manifest.git -b morty
    $ repo sync

Note that the default settings for bblayers.conf and local.conf may change
between branches.  If the environment was originally setup with e.g.
_TEMPLATECONF=meta-hiiaka-extras/conf_, check the _*.sample_ files in that
directory for any corresponding changes needed to the settings in
 _build/conf/_.

To get back to the known stable version, type:

    $ repo init -u git://github.com/hiiaka/yocto-manifest.git -b rocko
    $ repo sync

    
To learn more about repo, look at [Repo Command Reference](https://source.android.com/source/using-repo "Using repo")
