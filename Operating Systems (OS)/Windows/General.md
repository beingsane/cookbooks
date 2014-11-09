## Show platform architecture

	wmic os get osarchitecture

## File

Show file info.

    file -L filename.exe

## Make link

Creates a directory symbolic link.

	mklink /D link target

Creates a hard link instead of a symbolic link.

	mklink /H link target

Creates a Directory Junction.

	mklink /J link target