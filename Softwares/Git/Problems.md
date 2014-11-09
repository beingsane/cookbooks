## Msysgit Issue

0 [main] us 0 init_cheap: VirtualAlloc pointer is null, Win32 error 487
AllocationBase 0x0, BaseAddress 0x68570000, RegionSize 0xE0000, State 0x10000
C:\Tools\cmder\vendor\msysgit\bin\sh.exe: *** Couldn't reserve space for cygwin's heap, Win32 error 0

	cd C:\Tools\cmder\vendor\msysgit\bin

Exec command

	rebase.exe -b 0x50000000 msys-1.0.dll
