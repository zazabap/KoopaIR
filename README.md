# KoopaIR
Compiler and Intermediate Representation using C++

## Process
The overall process including
1. Compile SysY to Koopa IR 
2. Compile Koopa IR on RISC-V assembly. 

## Environment Setup 

First, please run the following command to setup the docker environment. 
```
docker
docker pull maxxing/compiler-dev
docker run maxxing/compiler-dev ls -l /
```
Useful command to check status, add and remove the container. 

```
docker rm 
docker ps -a
```

To initialize the command when developing and debug:
```
docker run -it --rm -v /path/to/directory:/root/compiler maxxing/compiler-dev bash
```


<!-- docker run -it --rm -v /Users/shiwenan/Documents/KoopaIR:/root/compiler maxxing/compiler-dev bash -->


There are several framework for Koopa IR `koopa` and `libkoopa` both have the library infrastructure, to realize the `Koopa IR`'s generation, analysis and conversion. 

Testing how to run Koopa 
```
cd Preview
koopac hello.koopa | llc --filetype=obj -o hello.o
clang hello.o -L$CDE_LIBRARY_PATH/native -lsysy -o hello
./hello
```

and test how to run the assembly 
```
cd Preview 
clang hello.S -c -o hello.o -target riscv32-unknown-linux-elf -march=rv32im -mabi=ilp32
ld.lld hello.o -L$CDE_LIBRARY_PATH/riscv32 -lsysy -o hello
qemu-riscv32-static hello
```


