
# Autohotkey

### send delete + f9 

^+d::
MsgBox, 4, Confirm, Are you sure you want to send Delete + F9?
IfMsgBox, Yes
{
  SendInput, {Delete}
  SendInput, {F9}
}
return



### HCL Notes - Move selected mail to a folder name starting with 'a' using CTRL+6 

```
^6::
SetKeyDelay,50
WinActivate, ahk_class SWT_Window0
SEND,!ALM
Sleep, 500
SEND, {ENTER}
return
```


### HCL Notes - Open java debug console using shortcut CTRL+J

```
;open java debug console
^j::
SetKeyDelay,50
WinActivate, ahk_class SWT_Window0
SEND,!o
Sleep, 500
SEND,j
return
```

### HCL Notes - Kill all notes processes, also works with Notes 64bits
```
Run, C:\notes\nsd.exe -kill
```


### HCL Notes - Switch to another location in notes starting with 'c' using Shortcut CTRL+2
```
^2::
SetKeyDelay,50
WinActivate, ahk_class SWT_Window0
SEND,!FL{ENTER}
SEND,c{DOWN 2}{ENTER}
return
```

### HCL Notes - Open replicator page in Notes using shortcut ALT+R

```
!r::
#IfWinActive ahk_class SWT_Window0
	run notes:///ClientBookmark?OpenReplication
#IfWinActive
return
```

## Login to Watchguard VPN using shortcut CTRL+1
```
^1::
Run,C:\\Program Files (x86)\\WatchGuard\\WatchGuard Mobile VPN with SSL\\wgsslvpnc.exe
WinWaitActive,"WatchGuard Mobile VPN with SSL",,2
Send,{TAB}{TAB}enterpasswordhere{TAB}{ENTER}
return
```

## Run a HCL Notes agent from windows using powershell

$env:path += ";C:\notes;c:\notes\data"
$session = New-Object -ComObject Lotus.NotesSession
$session.Initialize("")
$db = $session.getDatabase("","db.nsf")
$agent = $db.getAgent("Testagent")
$agent.run()

