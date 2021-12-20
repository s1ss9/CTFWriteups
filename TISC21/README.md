Level 0

1. Complete the survey

Level 1

1. Scenario 1
2. Scratching the surface 1 - WAV file - Noticed only price is right music in left channel. Used audacity to turn off left channel, heard morse code. Removed left channel, uploaded to morsecode.world, -150 minimum volume. CSITISLOCATEDINSCIENCEPARK
3. Scratching the surface 2 - JPG file, just use exiftool.
4. Scratching the surface 3 - JPG file, binwalk to extract, strings to get the top text, rot13 for answer. NAFJRE GB GUVF PUNYYRATR VF URER NCCYRPNEEBGCRNE -> ANSWER TO THIS CHALLENGE IS HERE APPLECARROTPEAR

Up to here, completion time is approx 1h

5. Scenario 2 - Download windows VM
6. Scratching the surface 4 - What is the name of user? Open powershell
7. Scratching the surface 5 - What is the time of user's most recent login? Go to event viewer and search for Logon without Special logon and convert to GMT.
8. Scratching the surface 6 - 7z archive. Transfer file to local machine, pass throguh CRC32 hasher
9. Scratching the surface 7 - RIDs type wmic useraccount get name, sid
10. Scratching the surface 8 - Browsing history deleted, https://inloop.github.io/sqlite-viewer/ 2 visits to csit website, 0 to others.
11. Scratching the surface 9 - What is the label of the volume Z? Regedit > Computer\HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\MountPoints2\##VBoxSvr#vm-shared, answer is vm-shared.
12. Scratching the surface 10 - We are to find a file with the SHA1 hash being a certain value. So... get-childitem "C:/Users" -recurse -ErrorAction SilentlyContinue | where {$_.Name -ne "fuckpp.txt"} | % {
    Get-FileHash -Algorithm SHA1 $_.FullName
    $\_.FullName
    } -ErrorAction SilentlyContinue >fuckpp.txt

    Looks like the following was better, the above crashed often...

    Get-ChildItem -Path "C:/" -Force -Recurse -ErrorAction SilentlyContinue | ForEach-Object {Get-FileHash -Path $_.FullName -Algorithm SHA1 -ErrorAction SilentlyContinue} | Where-Object {$\_.Hash -eq "0D97DBDBA2D35C37F434538E4DFAA06FCCC18A13"}

Up to here, completion time is approx 6h, excluding the initial 1h.
