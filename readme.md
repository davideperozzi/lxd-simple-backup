# Very simple lxc backup script

This script allows you to create snapshots of a specific container everytime it's executed. 
It provides an auto cleanup of the containers which are older than the defined "retain time".
That's it. Nothin more, nothing less. Feel free to change it to your own needs.

## Installation

It's only one file, so you can get it like this: 

```shell
cd /to/a/custom/destination/lxd-simple-backup/
wget https://raw.githubusercontent.com/davideperozzi/lxd-simple-backup/master/backup.py
chmod +x ./backup.py
```

## Requirements

You just need **python > 3** and the latest lxc system installed.
Also make sure the script is **executable**.

## Usage

To run the script once, just execute the following command: 

```shell
./backup.py yourContainerName
```

To prevent the script from executing the lxc commands, just append this: 

```shell
./backup.py yourContainerName --dry-run 1
```

Everything else is covered by the help command: 

```shell
./backup.py yourContainerName --help
```

## Using a cronjob

If you want to execute the script every two hours you could add this to your crontab file: 
```
0 */2 * * * /opt/lxd-simple-backup/backup.py yourContainerName
```
> To open your crontab file simply call ```crontab -e```

## License
This script is open-sourced software licensed under the MIT license.
