# You will need to provide your own 32b static library for libbfd if you 
# want to cross compile to 32b intel from amd64. Simply installing
# the 32b library on top of a 64b system using apt-get breaks ubuntu.
#
# Note that the 64b version and 32b versions alike can process
# any ELF (from any architecture/OS/endianess).
#

CC := gcc # You can use clang too
CFLAGS := -W -Wall -Wextra -fpie -pie -fPIC -g3 -ggdb -O0 -I../../include

all::
	$(CC) $(CFLAGS) wld.c -o wld -lbfd
#	$(CC) $(CFLAGS) wld.c -o wld32 -m32 ../lib32/usr/lib/libbfd.a

	cp wld ../../bin/
#	cp wld32 ../../bin/
test:

clean:
	rm -f wld wld32 a.out

install:
	cp wld /usr/bin/wld
#	cp wld32 /usr/bin/wld32

uninstall:
	rm /usr/bin/wld -f
#	rm /usr/bin/wld32 -f
