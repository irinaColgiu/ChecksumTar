tarchecksum
===========
This module performs the checksums on all the files in a tar archive and compares them
against the checksums of the original files. In case the md5 sums don't match,
there will be an error message outputted. It doesn't check if the directory and the tar have identical files, it only reads the members of the tar and checks them against the members of the original files.
The checksum on the archive members is done by streaming from the tar the list of members and their metadata,
and computing the md5 checksum on each member after extracting it.

Example:

`$python tarcheck.py --tar_path /path/to/archive/archive.tar.bz2 --dir /path/to/the/archived/dir`

where:
* tar_path (Required) is the path to the tar archive
* dir (Required) is the path to the directory that has been archived
It gives an error if there are files in the archive that can't be found in the directory
given as input.

It uses < 100MB memory to run.


