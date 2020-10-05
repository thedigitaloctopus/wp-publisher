![Installation](https://raw.githubusercontent.com/vivithemage/wp-publisher/master/docs/wp-publisher-logo.png)

## About
A desktop app which helps speed up wordpress development and deployment on digitalocean servers.

It does this by allowing a user to:

1. Install a fresh installation of wordpress locally.
2. Publish a wordpress website to a new digitalocean server.

The goal is to make an open source alternative to ['local' by Flywheel](https://local.getflywheel.com/)

If you're working with a WAMP development stack and using a single digitalocean vps for each website you host this will almost certainly help you out! Take a look at the screenshots below.

![Installation](https://raw.githubusercontent.com/vivithemage/do-wp/master/docs/screenshot-install.png)

![Publish](https://raw.githubusercontent.com/vivithemage/do-wp/master/docs/screenshot-publish.png)


## Installation

To install dependancies do:

    pip install -r requirements.txt

failing that:

    pip install pyqt5 python-digitalocean paramiko pymysql


## Quick Start

Create the following directory structure:

    example.com/public_html
    example.com/SQL

Place the root (so copy and paste everything in the directory with wp-config.php in) into public_html.
Place the sql file into SQL and make sure the sql file has *the exact same name as the database name in wp-config.php*.

Enter the api key and the hostname and press 'start'.

After a minute or two you should find the logs tab has the ip and root password. Paste the ip into the browser to see the site live on a new digitalocean server and ssh in to make any tweaks.

## Supports

Tested and working on Windows 7 and 10.


## Contribute

There's a lot to do and all contributions are very welcome. Please get in touch if you are interested in contributing to the project. I'll do my best to assist!

The list below details some areas which could do with some attention.

* Add additional error checking on fields (current error checking is very basic).
* Add error checking to installation path folder (ensure it has public_html and SQL folder)
* Investigate issue with Digitalocean api failing to return data.
* Allow for more customization when installing.
* Push all logging to log window and log file.
* Create a stand alone exe and installer (see http://nuitka.net/ http://www.py2exe.org/)
* Integrate with additional cloud server providers (e.g. Amazon, Bytemark).
* Test on Mac and Linux
* Integrate with wordmove by creating a movefile.yml in the wordpress directory when initializing a new wordpress instance locally (https://github.com/welaika/wordmove)
* General improvements to the UI. Maybe an additional options button for people to fine tune the installation (e.g. specify new packages)
* Currently only supports the the ubuntu lemp digitalocean image. Adding support for other distros would be useful. This was done for speed. It would be 
* Integrate mysql backups. This has been partially done with: 


## Development notes

### Generating the GUI


The gui is created in qt creator using the deisnger feature. This is then saved and converted into a
python class by running the following command:

    pyuic5.exe -x .\front_end_design.ui -o front_end.py


### Compiling into standalone application

Download [pyinstaller](https://www.pyinstaller.org/)
    
    cd wp-publisher
    pyinstaller.exe --onefile wp-publisher.py --icon=logo.ico
    
That should then result in a standalone exe being created in the dist file. Try:

    ls dist
    
From here you can run the nsis script (installer.nsi) which will build the installer.
    
### Sponsors
    
WP Publisher is generously supported by [Jetbrains](https://www.jetbrains.com/) with licenses and free accounts for their products.


