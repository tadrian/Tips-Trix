
# Autohotkey


### Move selected mail to folder name starting with 'a' using CTRL+6

```
^6::
SetKeyDelay,50
WinActivate, ahk_class SWT_Window0
SEND,!ALM
Sleep, 500
SEND, {ENTER}
return
```


### Open java debug console using shortcut CTRL+J

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

### Kill all notes processes, also works with Notes 64bits
```
Run, C:\notes\nsd.exe -kill
```


### Switch to another location in notes starting with 'c' using Shortcut CTRL+2
```
^2::
SetKeyDelay,50
WinActivate, ahk_class SWT_Window0
SEND,!FL{ENTER}
SEND,c{DOWN 2}{ENTER}
return
```

### Open replicator page in Notes using shortcut ALT+R

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



