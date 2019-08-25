# AdGuardHome package for Debian and Ubuntu
Creates a Debian/Ubuntu package for `AdGuardHome`. 

`AdGuardHome` is a network-wide ads & trackers blocking DNS server.

For more information about `AdGuardHome`, please visit https://adguard.com/en/adguard-home/overview.html and https://github.com/AdguardTeam/AdGuardHome

## How to install
Select the package for your architecture (amd64, i386, armhf, arm64). 
```
wget -O adguardhome.deb https://github.com/adelolmo/adguardhome-debian/releases/download/v0.98.1/adguardhome_0.98.1_armhf.deb
sudo dpkg -i adguardhome.deb
```

### How to use

Use `systemd` to manage the service `adguardhome`.

```
sudo systemctl start adguardhome
sudo systemctl stop adguardhome
sudo systemctl restart adguardhome
```

By default the dashboard is accessible under the port `http://localhost:3000`.

### How to configure

The configuration file is located in `/etc/opt/adguardhome/AdGuardHome.yaml`.

The log output is created in `/var/log/adguardhome/adguardhome.log`.

AdGuardHome creates application files under `/var/opt/adguardhome` directory.

Instructions of how to configure `AdGuardHome` are out of the scope of this readme.
Refer to https://github.com/AdguardTeam/AdGuardHome/wiki for details about configuration.

## How to build

Clone the project.

```
git clone https://github.com/adelolmo/adguardhome-debian.git
```

Then run the `package` script to download the create the package.

```
./package armhf 0.97.1
```
The first parameter is the system architecture, it must be one of: amd64, i386, armhf, arm64. 

The second parameter is the version of `AdGuardHome`. You can find all the releases of `AdGuardHome` [here](https://github.com/AdguardTeam/AdGuardHome/releases). 

The debian package will be created under `build/releases`.
