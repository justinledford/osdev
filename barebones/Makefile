CC=./../i686-elf-4.9.1-Linux-x86_64/bin/i686-elf-gcc
AS=./../i686-elf-4.9.1-Linux-x86_64/bin/i686-elf-as

all: myos.bin

myos.bin: boot.o kernel.o
	$(CC) -T linker.ld -o $@ -ffreestanding -O2 -nostdlib $^ -lgcc

boot.o: boot.s
	$(AS) $^ -o $@

kernel.o: kernel.c
	$(CC) -c $^ -o $@ -std=gnu99 -ffreestanding -O2 -Wall -Wextra

clean:
	rm -rf boot.o kernel.o myos.bin
