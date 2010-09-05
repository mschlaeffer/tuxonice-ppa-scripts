.PHONY: 00list
00list:
	find . -maxdepth 1 -name Makefile -prune -o -name 00list -prune -o -type f -print \
		| sed -ne 's,\./\(.*\)\.dpatch,\1,p' | sort -n > $@
