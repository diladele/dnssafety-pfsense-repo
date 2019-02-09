# External repo for DNS Safety Filter for pfSense project

## How to create repo structure (only once)

The following steps assume you have FreeBSD 11 up and running. First, login into into console using normal user credentials (here we assume the user name is `builder`) and create the required folder structure.

	cd ~
    mkdir diladele
    cd diladele
    git clone git@github.com:diladele/dnssafety-pfsense-repo.git
    cd dnssafety-pfsense-repo

Now, retrieve the latest stable build of DNS Safety Filter into `dnssafety-pfsense-repo` folder.

    fetch http://packages.diladele.com/dnssafety/0.4.0.9E0B/amd64/release/freebsd11/dnssafety-0.4.0-amd64.txz

And create the required repo structure using `pkg` command.

	pkg repo .

After this command the following files will appear in the current folder.

    digests.txz
    meta.txz
    packagesite.txz
    dnssafety-6.4.0-amd64.txz

Commit them into git.

## How to publish new build of DNS Safety Filter into the repo



