README
======

Ubuntu automation
----------------
This project contains a handful of shell scripts to make your life with web development in Ubuntu easier.

The following items are included:
* [`BackupWebProjects.sh`](#backupwebprojectssh) is general purpose script to backup all web projects in any linux environment.
* [`SetupLinuxApacheMySQLPHP.sh`](#setuplinuxapachemysqlphpsh-applications) targets Ubuntu 64 bit 12.04 LTS computers. The script sets up local development environment for Linux-Apache-MySQL-PHP. Currently, additional tools are included as well - please refer to section "SetupLinuxApacheMySQLPHP.sh applications"
* [`SetupWebProject.sh`](#setupwebprojectsh) targets Ubuntu 13.10 computers. SetupWebProject.sh automates the setup of new web projects on Apache. Please refer to "SetupWebProject.sh applications" for more information
* `SetupDrush.sh` targetes Ubuntu 13.10 computers, because installation has specifics. `SetupDrush.sh` contains documentation in itself.
* [`SetupVMWarePlayer.sh`](#setupvmwareplayersh) has been tested on Ubuntu 13.10 computers, but should be executable on any version as well, since no specifics are included
* `ArchivesSetup.sh` is currently a placeholder to migrate the automation of downloading and installing programs coming as archives outside APT

BackupWebProjects.sh
--------
BackupWebProjects.sh automates the backing up of all web projects contained in a given linux environment
* Backup file contains a date description, convenient for daily backups
* Backup archive is generated to hold the projects
* The archive is stored within a folder from Copy cloud service, which automatically backups the file in the cloud
* All parameters of the backup automation can be changed to match different development environments and cloud backup service

SetupLinuxApacheMySQLPHP.sh applications
--------

Ubuntu fixes
* Install the package to fix missing skype icon on toolbar

Server environment
* apache2
* PHP5
* mySQL
* phpmyadmin

Tools
* JDK7
* Netbeans
* git
* Google Chrome
* subversion (SVN)
* DropBox
* VirtualBox
* Skype
* Sublime Text 3

**Note:**
Note that some of the applications are downloaded via external sources (skype, Chrome, etc.), while others are directly installed via the Advanced Packaging Tool (APT).

External applications are downloaded on the Desktop, so that user can install them manually if necessary.

The following applications will also be included in the tools' set
* nodeJS
* XDebug

SetupWebProject.sh
--------
SetupWebProject.sh automates the setup of new web projects on Apache in the following way:
* takes user input for name of the project - i.e. example.dev
* creates a project folder at /var/www with input project name
* creates an example file with HTML in the root folder of the newly created project folder
* sets necessary permissions on new project files and folders to be editable
* populates initial index.html file with HTML with welcoming instructions
* setups the necessary folders at /etc/apache2 folders for new virtualhost project
* enables the new virtualhost project site using default functions from apache2
* includes a new entry inside /etc/hosts file for reaching the project with pretty url
* restarts apache2 service

SetupVMWarePlayer.sh
--------
SetupVMWarePlayer.sh prepares you to manage virtual machines on your PC:
* Downloads the player
* Extracts the archive
* Runs the install
* Clears up installables
* Runs the newly installed player

Installation
------------
Assume that the script file you are going to use is called "script.sh".
Here are the steps you need to take to start the script:
* Download script.sh
* Open the terminal with `Ctrl+Atl+t`
* Change to the folder where you have downloaded the file
* Add permissions to the file by `chmod +x ./script.sh`
* Run by typing `./script.sh`
* Read the command line carefully and make your choices! :)

Modifying the list of applications to be installed
------------
The following lists can be modified to fit your personal needs:
* `archiveApps` at `SetupLinuxApacheMySQLPHP.sh` contains the list of programs taken as archives outside APT
* `appsList` at `SetupLinuxApacheMySQLPHP.sh` contains the list of programs taken as shell scripts or .deb packages outside APT
* `repoAppsList` at `SetupLinuxApacheMySQLPHP.sh` contains the list of programs to be installed from APT

Plans for the project "Ubuntu automation"
------------
Other web development helpers are planned:
* Separete scripts for tools setup to be outside the `SetupLinuxApacheMySQLPHP.sh` script
* Script to setup Drupal projects quickly
* Script to setup WordPress projects quickly
* Building Drupal projects with continuous integration
