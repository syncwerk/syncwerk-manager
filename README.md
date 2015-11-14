# Seafile Manager (Alpha Version)
The Seafile manager provides easy management for various Seafile related tasks from the Linux command line. It makes heavy usage of the Seafile WebAPI.

Due to the very early state of the Seafile manager things will very likely break and therefore can harm productive Seafile server installation severely. Data loss is very well possible at this stage. If you care about your data, don't use it on production systems.

## Requirements
- curl
- openssl
- git


## Install
Follow the instructions as stated below.

### Download
```
cd /opt/
git clone https://github.com/SeafileDE/seafile-manager.git
chmod +x seafile-manager/seafile-manager
```

### Save Seafile admin credentials
- Retrieve Seafile admin token as explained at http://manual.seafile.com/develop/web_api.html
- Save the admin credentials to ~/.seafile-manager-credentials as shown in the following format:

```
cat ~/.seafile-manager-credentials
TOKEN=12345678901234567890123456789
PROTO=https
ADDRESS=app.seafile.de

DBHOST=localhost
DBUSER=seafile
DBPASS=secret
```

- Restrict access of ~/.seafile-manager-credentials to the owner
```
chmod 400 ~/.seafile-manager-credentials
```

### Create symlink
```
ln -s /opt/seafile-manager/seafile-manager /usr/local/bin/seafile-manager
```

## Usage
These following self-explanatory actions have been added already but not heavily tested:

```
seafile-manager {get-account-info | check-account-info | create-account | update-password | enable-admin | disable-admin | activate-account}
```

## Infos about the Seafile Web API
- http://manual.seafile.com/develop/web_api.html

## Todos

- Add info on how to retrieve the admin token to README.md
- Add more actions
- Search for FIXME's and fix ;-)

## Feedback
