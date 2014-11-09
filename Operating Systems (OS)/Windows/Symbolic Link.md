# Error

The symbolic link cannot be followed because its type is disabled

	fsutil behavior query SymlinkEvaluation

Set

	fsutil behavior set SymlinkEvaluation R2R:1
	fsutil behavior set SymlinkEvaluation L2L:1 R2R:1 L2R:1 R2L:1

Show

	fsutil behavior query SymlinkEvaluation
