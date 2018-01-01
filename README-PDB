
Oracle updated OH/rdbms/admin/awrrpt.sql so that AWR reports may be run against a PDB

Here are simple changes to enable using SLOB in a 12.2 PDB.

This may also work against 12.1 databases if run using a 12.2 full client, but I have not yet tried that.


# .slob.env

This file contains connect strings for use with a PDB on the local server

# runit.sh

Calls .slob.env to set environment

Sets the view_loc substitution variable to AWR_PDB so an AWR report will be generated for a PDB
(12.2 AWR reports only)


# setup.sh

Commented out the code that exits if the database is a [CP]DB.

There are cleaner ways to do this, but for now this works.

Calls .slob.env to set environment



