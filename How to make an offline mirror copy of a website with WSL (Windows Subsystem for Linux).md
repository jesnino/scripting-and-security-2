# How to make an offline mirror copy of a website with WSL (Windows Subsystem for Linux)
## Bash, PowerShell 
### URL: https://www.jesusninoc.com/2018/06/09/how-to-make-an-offline-mirror-copy-of-a-website-with-wsl-windows-subsystem-for-linux/
```PowerShell
bash -c "wget --mirror --convert-links --html-extension --wait=2 -o log https://www.jesusninoc.com"

```
```Shell
--mirror
    Turn on options suitable for mirroring. This option turns on 
    recursion and time-stamping, sets infinite recursion depth,
    and keeps FTP directory listings. It is currently equivalent to 
    ‘-r -N -l inf --no-remove-listing’. 

--convert-links
    After the download is complete, convert the links in the document
    to make them suitable for local viewing.

--html-extension

-o foo
    write "log" output to a file named "foo"

--wait=seconds
    Wait the specified number of seconds between the retrievals.
    Use of this option is recommended, as it lightens the server load 
    by making the requests less frequent.

```
