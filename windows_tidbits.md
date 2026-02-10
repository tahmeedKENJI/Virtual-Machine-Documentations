# WINDOWS HELPFUL TIPS
<br>

The purpose of this document is to gather as much helpful tips as I can on ``windows shell commands``. The following contains commands that I have found and used in various situations and thought that I should keep it safe somewhere. Any soul benefitted by this other than me is more than welcome! <br>
<br>

### February 10, 2026
Found this very useful command that **SHOWS DISK USAGE OF DIRECTORIES INSIDE THE CURRENT DIRECTORY**<br>
**shell**: ``windows powershell``<br>
```
Get-ChildItem | Where-Object {$_.PSIsContainer} | ForEach-Object {"{0:N2} MB - {1}" -f ((Get-ChildItem $_.FullName -Recurse | Measure-Object -Property Length -Sum).Sum / 1MB), $_.Name}
```
<br>

*p.s.: This markdown file also marks (pun intended) my interaction with* ``markdown`` *files. Feel free to inspect it.*
