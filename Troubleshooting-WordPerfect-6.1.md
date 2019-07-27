File handles need to equal 80 in CONFIG.SYS. ie...FILES=80

Temp dir must exist and be SET=C:\temp or whatever.

Things to try:

Delete wpcset.bif. WP will create a fresh one.

If weird errors are occuring copy a working C:\Windows\reg.dat off of another computer

You can also delete all of the temp files in the set temp dir.

If you are getting the error. "Can't find SHWINB20.DLL" You should re-install WP6.1 from the install source.\WP61\SETUP.EXE. It should work after reinstallation. 