To see if an existing profile already exists, run:

 Test-Path $profile

If False is returned, a profile does not exist.

To create a new profile, run:

 New-Item -Path $profile -ItemType File -force
 notepad $profile

Enter any functions or aliases and save.
