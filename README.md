# External repo for DNS Safety Filter for pfSense project

## How to create repo structure (only once)

The following steps assume you have FreeBSD 11 up and running. First, login into into console using normal user credentials (here we assume the user name is `builder`) and create the required folder structure.

	cd ~
    mkdir diladele
    cd diladele
    git clone git@github.com:diladele/dnssafety-pfsense-repo.git
    cd dnssafety-pfsense-repo

Now, retrieve the latest stable build of DNS Safety Filter into `dnssafety-pfsense-repo` folder.

