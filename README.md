###This is the simple  way to build you personal  nas media based on PlexTV server

******
## Install
**Note what you need installed docker and docker-compose on your host**

1. Clone repository
   `git clone https://github.com/TomMaSS/docker-plex-deluge-nextcloud.git`

2. Rename .env_example
`    mv .env_example .env`

3. Rename myncs_example
`mv ./builds/cron/myncs.exmpl  ./builds/cron/myncs`

4. Edit ./builds/cron/myncs and .env with your personal variables and paths

********
###.env

| Variable  | Value  |
| :------------ | :------------ |
|MEDIA_DIR= |  Main media_content directory |
|DELUGE_DIR=  |Deluge main directory |
|DELUGE_WATCH_DIR= |Deluge watching directory |
|PLEXPY_DIR= |PlexPy main directory|
|PLEX_DIR= |  Plex main directory|
|NEXTCLIENT_DIR= | Directory where nexctloud client will sync files|

###./builds/cron/myncs

| Variable  | Value  |
| :------------ | :------------ |
| **local:** | your_directory_to_store_sync_files|
|** remote: **| https://nextcloud.your.site |
|** username: **| your_user |
| **exclude_file: **| /opt/nextcl-sync-exclude.lst |
| **password: **| user_password |

### Run docker-compose

`docker-compose up  -d`