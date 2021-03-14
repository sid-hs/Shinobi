# We moved to GitLab!
## https://gitlab.com/Shinobi-Systems/Shinobi

Shinobi Pro

(Shinobi Open Source Software)
Shinobi is the Open Source CCTV Solution written in Node.JS. Designed with multiple account system, Streams by WebSocket, and Direct saving to MP4. Shinobi can record IP Cameras and Local Cameras.

Install and Use

Installation : http://shinobi.video/docs/start

Post-Installation Tutorials : http://shinobi.video/docs/configure

Troubleshooting Guide : https://hub.shinobi.video/articles/view/v0AFPFchfVcFGUS



Docker

Install with Docker : https://gitlab.com/Shinobi-Systems/Shinobi/-/tree/dev/Docker



"is my camera supported?"
Ask yourself these questions to get a general sense.

Does it have ONVIF?

If yes, then it may have H.264 or H.265 streaming capability.


Does it have RTSP Protocol for Streaming?

If yes, then it may have H.264 or H.265 streaming capability.


Can you stream it in VLC Player?

If yes, use that same URL in Shinobi. You may need to specify the port number when using rtsp:// protocol.


Does it have MJPEG Streaming?

While this would work in Shinobi, it is far from ideal. Please see if any of the prior questions are applicable.


Does it have a web interface that you can connect to directly?

If yes, then you may be able to find model information that can be used to search online for a streaming URL.



Configuration Guides : http://shinobi.video/docs/configure

Asking for help

General Support : https://shinobi.community

Please be sure to read the #guidelines channel after joining.


Business Inquiries : business@shinobi.video or the Live Chat on https://shinobi.video



Support the Development
It's a proven fact that generosity makes you a happier person :) https://www.nature.com/articles/ncomms15964
Get a Mobile License to unlock extended features on the Mobile App as well as support the development!

Shinobi Mobile App : https://cdn.shinobi.video/installers/ShinobiMobile/

Get a Mobile License : https://licenses.shinobi.video/subscribe?planSubscribe=plan_G31AZ9mknNCa6z



Why make this?
http://shinobi.video/why

Author
Moe Alam, Shinobi Systems
Shinobi is developed by many contributors. Please have a look at the commits to see some of who they are :)
https://gitlab.com/Shinobi-Systems/Shinobi/-/commits/dev

Support the Development
Ordering a certificate or support package greatly boosts development. Please consider contributing :)
http://shinobi.video/support

Links

Articles : http://hub.shinobi.video/articles

Documentation : http://shinobi.video/docs

Features List : http://shinobi.video/features

Some features may not be listed.


Donation : http://shinobi.video/docs/donate

Buy Shinobi Stuff : https://licenses.shinobi.video

User Submitted Configurations : http://shinobi.video/docs/cameras

Features : http://shinobi.video/features

Reddit (Forum) : https://www.reddit.com/r/ShinobiCCTV/

YouTube (Tutorials) : https://www.youtube.com/channel/UCbgbBLTK-koTyjOmOxA9msQ

Discord (Community Chat) : https://discordapp.com/invite/mdhmvuH

Twitter (News) : https://twitter.com/ShinobiCCTV

Facebook (News) : https://www.facebook.com/Shinobi-1223193167773738/?ref=bookmarks



Requirements

    These requirements will be installed for you with The Ninja Way. The Ninja Way is the recommended way to install. It will allow ease in updating as well as changes to the code.

    Node.js (12+), FFmpeg (3.3+), and MariaDB (10.4+) are the main components that Shinobi needs. With the Ninja Way it is expected that all these requirements will be fulfilled for you.

    To get the best experience and most support it is suggested that you install on a dedicated machine with Ubuntu 19.10 then install Shinobi the Ninja Way.

    Friendly Warning : Avoid Docker. If you can use a VM if you must use a shared environment.


    Warning : The Ninja Way installs from source code. Which means many libraries from other sources are going to be installed aswell.

The easiest way to install from source, directly on metal, is through git. The following operating systems are supported.

    Ubuntu 19.10

    CentOS 8

    MacOS 10.7(+)

    Become root to use the installer and run Shinobi. Use one of the following to do so.

        Ubuntu 19.10

        sudo su

        CentOS 8

        su

        MacOS 10.7(+)

        su

    Download and run the installer.

    bash <(curl -s https://gitlab.com/Shinobi-Systems/Shinobi-Installer/raw/master/shinobi-install.sh)





Ubuntu : The Easier Way

This installer works well with Ubuntu 17.10.1

    Open Terminal.

    Become root.

    sudo su

    Install git command line library.

    apt install git -y

    Pull the repository.

    git clone https://gitlab.com/Shinobi-Systems/Shinobi.git Shinobi

    Open Shinobi directory.

    cd Shinobi

    Start the installer

    chmod +x INSTALL/ubuntu.sh && INSTALL/ubuntu.sh

    Packages will be installed. MariaDB will ask to create a password on first installation.

    Once complete. Open up http://localhost:8080 in your browser.

        Note : if you are installed on a remote computer open up the IP in your web browser.

    Login at http://your.shinobi.video/super.

    Username : admin@shinobi.video
    Password : admin

    You should now be able to manage accounts

    To Update Shinobi :

    Update Shinobi via Terminal

CentOS, Fedora, RHEL : The Easier Way

This installer works well with CentOS 7.

    Open Terminal.

    Download and Install Node.js, NPM.

    sudo yum update
    sudo yum install curl -y
    curl --silent --location https://rpm.nodesource.com/setup_12.x | bash -
    sudo yum install nodejs npm -y

    Install git command line library.

    yum install git -y

    Pull the master repository.

    git clone https://gitlab.com/Shinobi-Systems/Shinobi.git Shinobi

    Open Shinobi directory.

    cd Shinobi

    Start the installer

    chmod +x INSTALL/centos.sh && INSTALL/centos.sh

    Packages will be installed. MariaDB will ask to create a password on first installation.

    Once complete. Open up http://localhost:8080 in your browser.

        Note : if you are installed on a remote computer open up the IP in your web browser.

    Login at http://your.shinobi.video/super.

    Username : admin@shinobi.video
    Password : admin

    You should now be able to manage accounts

    To Update Shinobi :

    Update Shinobi via Terminal

Account Management
Set up Superuser Access

Rename super.sample.json to super.json. Run the following command inside the Shinobi directory with terminal. Passwords are saved as MD5 strings. You only need to do this step once.

cp super.sample.json super.json

Login at http://your.shinobi.video/super.

Username : admin@shinobi.video
Password : admin

You should now be able to manage accounts
Set up Sub-Accounts

Login at http://your.shinobi.video/admin. With the main account of the group. If a sub account is used to login to this page it will be directed to the regular dashboard.
Clean up
Set up the cron file

    Run cron.js to get data about how much space is used and to clear old videos.

    pm2 start cron.js

Updating Shinobi
Getting the latest files

There were multiple ways to do this, now there is only one recommended way to do it. Please follow the link below.

    How to Update Shinobi Manually from Terminal

Daemonize and Startup
Keep running and on boot

    Start camera.js and cron.js then run check to see they are running under PM2.

    pm2 start camera.js
    pm2 start cron.js
    pm2 list

    After camera.js and cron.js are started you can run the following to start them on boot.

    pm2 startup
    pm2 save

Configuration
Done Installation

Confirguring Shinobi after Installation
Default Login

Login at http://your.shinobi.video/super.

Username : admin@shinobi.video
Password : admin

You should now be able to manage accounts

Update Shinobi via Terminal
Configuration File
conf.json

conf.json is the file that you create from conf.sample.json during the install process using the following command from inside the Shinobi directory.

cp conf.sample.json conf.json

Anyway! on to what’s really important. What’s in the file itself. This is the contents of conf.sample.json.

{
    "port": 8080,
    "addStorage": [
        {"name":"second","path":"__DIR__/videos2"}
    ],
    "ssl":{
       "key":"/path/to/key/file",
       "cert":"/path/to/cert/file"
    },
    "db": {
        "host": "127.0.0.1",
        "user": "majesticflame",
        "password": "",
        "database": "ccio",
        "port":3306
    },
    "mail":{
        "service": "gmail",
        "auth": {
            "user": "your_email@gmail.com",
            "pass": "your_password_or_app_specific_password"
        }
    },
    "cron":{
        "key":"change_this_to_something_very_random__just_anything_other_than_this"
    },
    "pluginKeys":{
        "Motion":"change_this_to_something_very_random____make_sure_to_match__/plugins/motion/conf.json"
    }
}

Available Options for conf.json
Options 	Required 	Type 	Description
cpuUsageMarker 	no 	string 	The marker that is used to search for CPU usage in top command. Default is %Cpu. Some systems, like Puppy Linux, require it be set to CPU.
defaultMjpeg 	no 	string 	A path leading to a JPEG file. This default image is needed for when the camera cannot provide frames.
doSnapshot 	no 	boolean 	By default the snapshot in the top left open its own FFMPEG process for a moment to get a single frame, You can avoid this by turning on JPEG API or setting this option to false.
updateKey 	no 	string 	For updating by API.
streamDir 	no 	string 	default is /dev/shm/streams/. Remember to end with /. Leave it undefined or null to use default. Be careful in using HLS as Stream Type. This directory should be set as somewhere in RAM
videosDir 	no 	string 	default is videos/ in the Shinobi directory. Remember to end with /. Leave it undefined or null to use default.
windowsTempDir 	no 	string 	default is C:/Windows/Temp. If your system is not located on the C: drive then you must add this option in your conf.json file.
DropboxAppKey 	no 	string 	Future releases will hide dropbox functions when this key is left null.
ip 	no 	string 	IP that is used for the Shinobi server instance. Default is undefined, which will tell the webserver to automatically choose.
port 	yes 	int 	Port that is used for the Shinobi server instance. Default is 8080
utcOffset 	yes 	string 	Timezone that matches your SQL database.
db 	yes 	object 	The login information for the SQL database
db.host 	yes 	string 	The IP address or domain name. Default is 127.0.0.1
db.user 	yes 	string 	The user name. Default is majesticflame.
db.password 	yes 	string 	The password. Default is no password.
db.database 	yes 	string 	The database name. Default is ccio.
db.port 	yes 	int 	The port number for Shinobi. Default is 3306.
cron 	no 	object 	The object that contains some options for cron.js
cron.deleteOld 	no 	boolean 	cron will delete videos older than Max Number of Days per account. Default is true.
cron.deleteNoVideo 	no 	boolean 	cron will delete SQL rows that it thinks have no video files. Default is true.
cron.deleteOverMax 	no 	boolean 	cron will delete files that are over the set maximum storage per account. Default is true.
mail 	no 	object 	If your Email account uses 2-Step Authentication, like Gmail, then you will be require to create an Application Password.
ssl 	no 	object 	If you would to use SSL (Encryption) you can include this object.
ssl.key 	yes* 	string 	Required if SSL object is present. This is a reference to a file that usually ends in .key.
Example : ssl/server.key will direct to a folder named ssl inside your Shinobi directory.
ssl.cert 	yes* 	string 	Required if SSL object is present. This is a reference to a file that usually ends in .crt.
Example : ssl/server.crt will direct to a folder named ssl inside your Shinobi directory.
ssl.passphrase 	yes* 	string 	If your key and certificate use a passphrase you must define it or SSL will not start.
ssl.port 	no 	int 	This is the port SSL will listen on. If option is undefined 443 will be used.
language 	no 	string 	Default is en_CA. You can check the langauges folder inside the Shinobi directory for more options. You can make more by using node tools/translateLanguageFile.js.
addStorage 	no 	object 	View the sample above for how to structure this object.
passwordType 	no 	string 	This can be sha256, sha512, or md5. md5 is the default.
passwordSalt 	yes* 	string 	This is only needed if passwordType is set to sha512.
