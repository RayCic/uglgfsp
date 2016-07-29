# Unofficial GOG Linux Grim Fandango Remastered SaveDir Patch
This project is intended to create solution for following long standing bug of GOG Grim Fandango Remastered Linux version.
## BUG
Game try to write user's data (configuration files, saved games) in place where it is installed instead of user's home directory.
## Solution
To solve this bug small patch for game's executable is developed.
## IANAL
WARNING! Using this patch may be illegal in some countries. Consult your lawyer.

In my opinion for me developing this patch is not illegal, because I live in Latvia where reverse engineering is allowed for purpose of bug fixing if not explicitly disabled by copyright holder. I was unable to find such clause in GOG license.
## How-to
1. Go to directory where game is installed
2. Run command `md5sum GrimFandango`
3. Check returned code string. It must be exactly `8c8cfa2fb5061f9e32c8601eab31144d`. If code string you received differs then do not continue.
4. Install xdelta 3rd version. Sometimes it is called xdelta3.
5. Download to `/tmp` directory file `Unofficial-GOG-Linux-Grim-Fandango-SaveDir-Patch-v2.xdelta3` from this project.
6. Run command `xdelta3 -d -s GrimFandango /tmp/Unofficial-GOG-Linux-Grim-Fandango-SaveDir-Patch-v2.xdelta3 GrimFandango.new`
7. Run command `mv GrimFandango.new GrimFandango`
8. Run command `chmod 0755 GrimFandango`

Now game will use `~/.GrimF` directory as user's data storage
# License
Work is licensed under WTFPL-2 license
