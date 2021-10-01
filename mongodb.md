# Mongo DB

### Config file

    /etc/mongod.conf

### Log file

    /var/log/mongodb/mongod.log

(otherwise check the `logpath` variable in `mongod.conf`)

### Rotate log files
Archives the current log file and creates a new one

    mongosh
	use admin
	db.adminCommand({logRotate:1})

## Commands

### List databases

    use admin
	db.adminCommand({listDatabases: 1})

### List collections

	use <database>
	db.runCommand({listCollections: 1})
OR

	show collections

## Status

    sudo systemctl status mongod

	sudo systemctl stop mongod

	sudo systemctl restart mongod

	sudo systemctl start mongod

(if server isn't found)

    sudo systemctl daemon-reload