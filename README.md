# violation_shaming_utils
Utilities to better run violation_shaming.


## db updating utilities ##
Violation_shaming operates on a hosted Postgres database, and does not have a
connection with the Open KC data store. Thus, we must manually update it.

These utilities are designed to act like a package manager (aptitude, homebrew, 
chocolatey, etc.): first they see if an update will even change anything on the
system; then, if the user desires, they actually update the database with new
information from the internet.

### dbsourceupdate ###
Polls the Open KC data store to see if an upgrade is needed.

### dbsourceupgrade ###
If dbsourceupdate says that an upgrade is needed, we will pull .csv files to 
obtain the data. An archive of the old data will then be created, and the 
new data will be placed in database tables.
