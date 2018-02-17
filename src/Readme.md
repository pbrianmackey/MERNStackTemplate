# About

Boilerplate for getting up and running quickly with a MERN environment.

# Install

xcode-select --install # A High Sierra thing.  Install.  
brew update
brew install mongodb

# Setup mongodb:

1. Install to default directory.  E.G. `sudo mkdir -p /data/db`
2. Setup permissions: `sudo chown -R ``id -un`` /data/db`


# At Terminal run:

Run the mongo daemon in one terminal:  `mongod`  # ctrl-c to exit
Run the mongo shell in another:  `mongo`   # quit() to exit

# Make a Configuration file

1.  mkdir db (Perhaps a new repo)
2.  create db\mongod.conf
3.  launch mongod -f db\mongod.conf # path is relative to where you run mongod from


A MERN stack template.  Can be used as a starting point for MERN stack development.  And also interesting JavaScript tidbits.


# Technology Stack

- MongoDB (DB repo)
- Express
- React (This repo)

# Planned
- Webpack

# Other
- Alternative:  http://mern.io/

# Useful mongo shell cmds

- show dbs # local is for internal use by mongo
- use DB_NAME # switch databases
- db # show which db we are connected to
- help


# run command without interactive shell
### Examples
# This command will be useful to schedule creation of a new log after a certain time period
# otherwise mongo will just continously append to the same log
- mongo serverName/dbName --eval "db.runCommand({logRotate:1})"
- mongo server1 someFile.js #run a script
- mong server1 someFile.js --shell # run the script and remain in shell mode
- mongo serverName/dbName --eval "printjson(db.runCommand({logRotate:1}))"

# Useful javascript files to run

```
var userCount = function() {
    var count = db.Users.count();

    var entry = {_id: Date(), n: count};

    db.UserCountHistory.save(entry);

    print("\nToday's User Count: " + entry.n);
};

userCount();
```
