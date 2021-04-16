# fix_exfat_drive
Fix corrupted exFAT disk macOS/OSX
exFAT support on macOS seems to have some bugs because my external drives with exFAT formatting will randomly get corrupted.

Disk Utility is unable to repair this at first, but the fix is this:

Use diskutil list to find the right drive id.
You want the id under the IDENTIFIER column, it should look like disk1s1
Run sudo fsck_exfat -d <id from above>. eg sudo fsck_exfat -d disk1s3
-d is debug so you'll see all your files output as they're processed.
Answer YES if it gives you the prompt Main boot region needs to be updated. Yes/No?
Open Disk Utility and you should be able to repair here successfully.
See the apple man page below for details on the fsck_exfat utility.

