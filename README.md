# Syncwerk Manager (Alpha Version)
The Syncwerk manager provides easy installation of the Syncwerk server and management for various Syncwerk related tasks from the Linux command line. It makes heavy usage of the Syncwerk WebAPI.

Due to the very early state of the Syncwerk manager things will very likely break and therefore can harm productive Syncwerk server installation severely. Data loss is very well possible at this stage. If you care about your data, don't use it on production systems.

All actions are logged to `~/syncwerk-manager_${SERVER_ADDRESS}).log`


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
git clone https://github.com/syncwerk/syncwerk-manager.git
chmod +x syncwerk-manager/syncwerk-manager
```

### Create ~/.syncwerk-manager-conf configuration file
```
cp syncwerk-manager/dev/syncwerk-manager-example-conf ~/.syncwerk-manager-conf
```

Restrict access of ~/.syncwerk-manager-conf to the owner
```
chmod 400 ~/.syncwerk-manager-conf
```

- Retrieve Syncwerk admin token as explained at http://manual.syncwerk.com/develop/web_api.html
- Save the TOKEN and connection setting to ~/.syncwerk-manager-conf as shown in the following format:
- Review the settings in ~/.syncwerk-manager-conf and change to reflect your setup


### Create symlink
```
ln -s /opt/syncwerk-manager/syncwerk-manager /usr/local/bin/syncwerk-manager
```


## Usage / Actions
These following self-explanatory actions have been added already but not heavily tested:

```
syncwerk-manager { check-my-account-info | get-account-info | create-account | update-password \
| enable-admin | disable-admin | activate-account | deactivate-account | migrate-account \
| delete-account | update-note | update-storage | backup-database | check-library-integrity \
| repair-library-integrity | enable-library-sync-after-repair | export-library-to-filesystem \
| install-syncwerk-professional-on-debian }
```


## Update

```
cd /opt/syncwerk-manager
git pull https://github.com/syncwerk/syncwerk-manager.git
```


## Infos about the Syncwerk Web API
- http://manual.syncwerk.com/develop/web_api.html


## Todos

- Add info on how to retrieve the admin token to README.md
- Add more actions
- Search for FIXME's and fix ;-)
- Add expert installation mode for Syncwerk server
- Add Syncwerk server installation for other operating systems, besides Debian
- Add Syncwerk CE installation
- Refine logging abilities 


## License
Copyright 2015, Alexander Jackson <alexander.jackson@syncwerk.com>

This program is free software: you can redistribute it and/or modify
it under the terms of the [GNU Affero General Public License](http://www.gnu.org/licenses/agpl-3.0.html) as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Affero General Public License for more details.


## Where can I submit bugs or add suggestions?
Create an issue on Github or just reply in the [corresponding forum thread](https://forum.syncwerk.com/t/syncwerk-manager-alpha-version/3347).
