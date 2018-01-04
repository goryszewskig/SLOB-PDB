
Oracle updated OH/rdbms/admin/awrrpt.sql so that AWR reports may be run against a PDB

Here are simple changes to enable using SLOB in a 12.2 PDB.

There does not appear to be any way to make AWR reports work per PDB in 12.1

# slob.conf

A new variable AWR_SRC can be set to either 'AWR_PDB' or 'AWR_ROOT'

This variable controls some settings in runit.sh that make it work with a PDB.

# .slob.env

This file contains connect strings for use with a PDB on the local server

# runit.sh

Calls .slob.env to set environment

Sets the values of view_loc and awr_location substitution variables to AWR_PDB so an AWR report will be generated for a PDB
(12.2 AWR reports only)

The DBID value is also chosen from v$database based on whether a PDC (con_dbid) or a standard legacy database (dbid)

# setup.sh

Commented out the code that exits if the database is a [CP]DB.

Calls .slob.env to set environment



