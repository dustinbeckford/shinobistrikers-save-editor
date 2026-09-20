# Shinobi Striker Save Editor

This Windows editor works with the decrypted GVAS/UE4 save structure used by
the CUSA08789 Customizev003 save.

## how to use
On Windows, extract it and double-click RunTool.bat. You'll need Python 3 installed.

Then select your decrypted Customizev003, scan it, enter 500, and create the modified save.

## Current editing features

### Main counters
- ID_Counter_Money
- ID_Counter_TotalMoney
- ID_Counter_PlayerExperience

### Scrolls
- Discovers all `ID_Scroll_*` IntProperty entries in the save.
- Lets you edit any individual scroll entry.
- Includes a button to set every discovered scroll entry to 500.

The editor only changes the four-byte IntProperty value following an existing
property name. It does not insert/remove fields or change the file size.

## Workflow

1. Dump/decrypt your CUSA08789 save with Apollo.
2. Run `RunTool.bat`.
3. Select the decrypted `Customizev003`/GVAS save.
4. Scan it.
5. Edit money, XP, or individual scroll values.
6. Click Create Modified Save.
7. Re-encrypt/resign the resulting file with Apollo.
8. Keep the automatically created `.backup` until the modified save is confirmed.

The tool refuses ambiguous property matches instead of guessing.

## Notes

The observed save stores the relevant values as 32-bit little-endian IntProperty
values. The editor preserves the original file length.


Scroll limit: Individual scroll values are restricted to 0-500. The bulk scroll button sets discovered scroll entries to 500.

any questions? reach out to @dustinbeckford on x.
