## Autoruns

### Overview
“Autoruns” is a term used to refer to the collection of locations Windows looks for processes to start during boot time. These locations are oftenly referred to as Autostart Extensibility Points (ASEP).  

ASEP’s are a very common way for both legitimate and malicious software to start on a Windows host. Defenders can often find the mechanisms malware is using to stay on a system by analyzing the data collected from using the Autorunsc tool. The mechanisms used by malware to stay on a system are commonly referred to as “Persistence”.

### Collection
```
.\autorunsc64.exe -accepteula -a * -s -h -c > .\autoruns-hostname.csv
```
**.\autorunsc64.exe** runs Autorunsc64.exe from the thumbdrive  
**-accepteula** accepts the End User License Agreement  
__-a *__ Show all startup locations  
**-s** Verify digital signatures  
**-h** Show file hashes  
**-c** Print as csv  
**> .\autoruns-hostname.csv** redirect output to a CSV on the thumb drive with a name that tells us what is and what system it was collected from.
