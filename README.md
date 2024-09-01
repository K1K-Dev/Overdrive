Overdrive is a NASM programming language compiled into assembler

Install:
Enter into the console:
-sudo apt update
-sudo apt -y install nasm

How to use:
In the downloaded project, create a file with the .ovd extension (Test.ovd) the entire code will be written in it

To compile a project, type in the console:
-./Overdrive
-Test.ovd(The name of yours .ovd file)
-nasm -f elf64 Test.ovd.asm -o Main.o
-gcc Main.o -static -o Main
-./Main


