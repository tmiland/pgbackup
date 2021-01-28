# pgbackup - Automated PostgreSQL Backup on Linux

```
                  ╔═══════════════════════════════════════════════════════════════════╗
                  ║                           Pg Backup.sh                            ║
                  ║                Automated PostgreSQL Backup on Linux               ║
                  ║                      Maintained by @tmiland                       ║
                  ║                          version: 1.0.0                           ║
                  ╚═══════════════════════════════════════════════════════════════════╝
```

[![GitHub release](https://img.shields.io/github/release/tmiland/pgbackup.svg?style=for-the-badge)](https://github.com/tmiland/pgbackup/releases)
[![licence](https://img.shields.io/github/license/tmiland/pgbackup.svg?style=for-the-badge)](https://github.com/tmiland/pgbackup/blob/master/LICENSE)
![Bash](https://img.shields.io/badge/Language-SH-4EAA25.svg?style=for-the-badge)

## Automated PostgreSQL Backup on Linux 

* MONTHLY BACKUPS
* WEEKLY BACKUPS
* DAILY BACKUPS
* FULL BACKUPS
* SCHEMA-ONLY BACKUPS
* GLOBALS BACKUPS

## Installation

#### Download and execute the script:

```bash
$ git clone https://github.com/tmiland/pgbackup.git
$ cd pgbackup
$ chmod +x pg_backup_rotated.sh && chmod +x pg_backup.sh
$ ./pg_backup.sh
```

# Default Configuration

### Edit preferences

```bash
# Optional system user to run backups as.  If the user the script is running as doesn't match this
# the script terminates.  Leave blank to skip check.
BACKUP_USER=root
 
# Optional hostname to adhere to pg_hba policies.  Will default to "localhost" if none specified.
HOSTNAME=localhost
 
# Optional username to connect to database as.  Will default to "postgres" if none specified.
USERNAME=postgres
 
# This dir will be created if it doesn't exist.  This must be writable by the user the script is
# running as.
BACKUP_DIR=/home/backup/database/postgresql/
 
# List of strings to match against in database name, separated by space or comma, for which we only
# wish to keep a backup of the schema, not the data. Any database names which contain any of these
# values will be considered candidates. (e.g. "system_log" will match "dev_system_log_2010-01")
SCHEMA_ONLY_LIST=""
 
# Will produce a custom-format backup if set to "yes"
ENABLE_CUSTOM_BACKUPS=yes
 
# Will produce a gzipped plain-format backup if set to "yes"
ENABLE_PLAIN_BACKUPS=yes
 
# Will produce gzipped sql file containing the cluster globals, like users and passwords, if set to "yes"
ENABLE_GLOBALS_BACKUPS=yes
 
 
#### SETTINGS FOR ROTATED BACKUPS ####
 
# Which day to take the weekly backup from (1-7 = Monday-Sunday)
DAY_OF_WEEK_TO_KEEP=5
 
# Number of days to keep daily backups
DAYS_TO_KEEP=7
 
# How many weeks to keep weekly backups
WEEKS_TO_KEEP=5
```

## Credits

Source: https://wiki.postgresql.org/wiki/Automated_Backup_on_Linux

## Donations 
- [PayPal me](https://paypal.me/milanddata)
- [BTC] : 33mjmoPxqfXnWNsvy8gvMZrrcG3gEa3YDM

## Web Hosting

Sign up for web hosting using this link, and receive $100 in credit over 60 days.

[DigitalOcean](https://m.do.co/c/f1f2b475fca0)

#### Disclaimer 

*** ***Use at own risk*** ***

### License

[![MIT License Image](https://upload.wikimedia.org/wikipedia/commons/thumb/0/0c/MIT_logo.svg/220px-MIT_logo.svg.png)](https://github.com/tmiland/pgbackup/blob/master/LICENSE)

[MIT License](https://github.com/tmiland/pgbackup/blob/master/LICENSE)
