# External repo for DNS Safety Filter for pfSense project

## How to publish new build of DNS Safety Filter into the repo

Here is how to publish new 0.4.0.3EFF build of DNS Safety into the pfSense repo. Open console and run the following commands.

    cd diladele/dnssafety-pfsense-repo/repo/FreeBSD:11:amd64
    fetch http://packages.diladele.com/dnssafety/0.4.0.3EFF/amd64/release/freebsd11/dnssafety-0.4.0-amd64.txz
    pkg repo .

Commit the following files into git and push to github.com.

    digests.txz
    meta.txz
    packagesite.txz
    dnssafety-0.4.0-amd64.txz


## How to install DNS Safety Filter using this repo in pfSense 2.4

Assuming you have pfSense 2.4 up and running, open console and run the following commands to install a reference to the DNS Safety Filter repo and install it. Note this only installs the DNS filtering daemon!

    fetch -q -o /usr/local/etc/pkg/repos/dnssafety.conf https://raw.githubusercontent.com/diladele/dnssafety-pfsense-repo/master/dnssafety.conf
    pkg update
    pkg install dnssafety


## How to create repo structure (only once)

The following steps assume you have FreeBSD 11 up and running. First, login into into console using normal user credentials (here we assume the user name is `builder`) and create the required folder structure.

	cd ~
    mkdir diladele
    cd diladele
    git clone git@github.com:diladele/dnssafety-pfsense-repo.git    

Now, retrieve the latest stable build of DNS Safety Filter into `dnssafety-pfsense-repo` folder and create the required repo structure using `pkg` command.

    cd dnssafety-pfsense-repo
    mkdir -p repo/FreeBSD:11:amd64
    cd repo/FreeBSD:11:amd64
    fetch http://packages.diladele.com/dnssafety/0.4.0.9E0B/amd64/release/freebsd11/dnssafety-0.4.0-amd64.txz
	pkg repo .

After this command the following files will appear in the `repo/FreeBSD:11:amd64` folder. Commit them into git and push to github.com.

    digests.txz
    meta.txz
    packagesite.txz
    dnssafety-0.4.0-amd64.txz

