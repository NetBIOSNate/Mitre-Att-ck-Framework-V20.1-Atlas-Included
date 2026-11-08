# S0231 - Invoke-PSImage

[Enterprise](../../../README.md) / [Tools](README.md)

[Invoke-PSImage](https://attack.mitre.org/software/S0231) takes a PowerShell script and embeds the bytes of the script into the pixels of a PNG image. It generates a one liner for executing either from a file of from the web. Example of usage is embedding the PowerShell code from the Invoke-Mimikatz module and embed it into an image file. By calling the image file from a macro for example, the macro will download the picture and execute the PowerShell code, which in this case will dump the passwords. (Citation: GitHub Invoke-PSImage)

[MITRE ATT&CK record](https://attack.mitre.org/software/S0231)

## Techniques used

- [T1027.009 - Embedded Payloads](../../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.009%20-%20Embedded%20Payloads/README.md)
- [T1027.003 - Steganography](../../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.003%20-%20Steganography/README.md)

## Used by

- [G0034 - Sandworm Team](../../Groups/G0034%20-%20Sandworm%20Team.md)

## Sources

- [GitHub Invoke-PSImage](https://github.com/peewpw/Invoke-PSImage)
