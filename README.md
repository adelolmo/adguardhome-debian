# AdGuardHome package for Debian
Creates a Debian package for `AdGuardHome`. 

`AdGuardHome` is a network-wide ads & trackers blocking DNS server.

For more information about `AdGuardHome`, please visit https://adguard.com/en/adguard-home/overview.html 
and https://github.com/AdguardTeam/AdGuardHome

## How to install
Select the package for your architecture (amd64, i386, armhf, arm64). 

    wget -O adguardhome.deb https://github.com/adelolmo/adguardhome-debian/releases/download/v0.102.0/adguardhome_0.102.0_armhf.deb
    sudo dpkg -i adguardhome.deb

### How to use

Use `systemd` to manage the service `adguardhome`.

    sudo systemctl start adguardhome
    sudo systemctl stop adguardhome
    sudo systemctl restart adguardhome

By default, the dashboard is accessible under the port `http://localhost:3000`.

### How to configure

The configuration file is located in `/etc/opt/adguardhome.yaml`.

The log output is created in `/var/log/adguardhome/adguardhome.log`.

AdGuardHome creates runtime application files under `/var/opt/adguardhome` directory.

Instructions of how to configure `AdGuardHome` are out of the scope of this readme.
Refer to https://github.com/AdguardTeam/AdGuardHome/wiki for details about configuration.

## How to build

    git clone https://github.com/adelolmo/adguardhome-debian.git
    make VERSION=0.105.2

The parameter `VERSION` is the version of `AdGuardHome`. 
You can find all the releases of `AdGuardHome` [here](https://github.com/AdguardTeam/AdGuardHome/releases). 

The debian package will be created under `build/releases`.

### Cross platform build

Use the parameter `ARCH` with one of the following supported architectures: amd64, i386, armhf or arm64.

    make VERSION=0.105.2 ARCH=armhf
