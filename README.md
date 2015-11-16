# Seafile Manager (Alpha Version)
The Seafile manager provides easy management for various Seafile related tasks from the Linux command line. It makes heavy usage of the Seafile WebAPI.

Due to the very early state of the Seafile manager things will very likely break and therefore can harm productive Seafile server installation severely. Data loss is very well possible at this stage. If you care about your data, don't use it on production systems.


## Requirements
- curl
- openssl
- git
- mariadb-client


## Install
Follow the instructions as stated below.


### Download
```
cd /opt/
git clone https://github.com/SeafileDE/seafile-manager.git
chmod +x seafile-manager/seafile-manager
```

### Create ~/.seafile-manager-conf configuration file
```
cp seafile-manager/dev/seafile-manager-example-conf ~/.seafile-manager-conf
```

Restrict access of ~/.seafile-manager-conf to the owner
```
chmod 400 ~/.seafile-manager-conf
```

- Retrieve Seafile admin token as explained at http://manual.seafile.com/develop/web_api.html
- Save the TOKEN and connection setting to ~/.seafile-manager-conf as shown in the following format:
- Review the settings in ~/.seafile-manager-conf and change to reflect your setup


### Create symlink
```
ln -s /opt/seafile-manager/seafile-manager /usr/local/bin/seafile-manager
```

## Usage
These following self-explanatory actions have been added already but not heavily tested:

```
seafile-manager { get-account-info | check-account-info | create-account | update-password | enable-admin | disable-admin | activate-account | deactivate-account | backup-database }
```

## Update

```
cd /opt/seafile-manager
git pull https://github.com/SeafileDE/seafile-manager.git
```

## Infos about the Seafile Web API
- http://manual.seafile.com/develop/web_api.html


## Todos

- Add info on how to retrieve the admin token to README.md
- Add more actions
- Search for FIXME's and fix ;-)


## License
Copyright 2015, Alexander Jackson <alexander.jackson@seafile.de>

This program is free software: you can redistribute it and/or modify
it under the terms of the [GNU Affero General Public License](http://www.gnu.org/licenses/agpl-3.0.html) as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Affero General Public License for more details.

## Where can I submit bugs or add suggestions?
Create an issue on Github or just reply in the [corresponding forum thread](https://forum.seafile-server.org/t/seafile-manager-alpha-version/3347).
