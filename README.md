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
