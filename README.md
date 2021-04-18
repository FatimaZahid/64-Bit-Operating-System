# 64-Bit-Operating-System
                           ********************HERE IS THE OUTPUT TO THE MENTIONED CODE FOR 64 BIT OS************************

<img src = "Screenshot_Output_SEECS LOGO.PNG"></img>

This respository holds all the source code for building x86_64 OS

                                                     **************Initials***************
Firstly, Docker and Qemu must be installed for this code to run 
Docker has containers. so it must be run first.
Path of QEMU should be added to environement variables
An editor, (VSCODE) would be required for compiling the codes 

                                   *********** Downloading Files for building an image*******************
- docker build buildenv -t myos-buildenv   //run in terminal (cmd)

                                                 *********FOR BUILDING:*************
- Linux or MacOS: `docker run --rm -it -v "$pwd":/root/env myos-buildenv`
 - Windows (CMD): `docker run --rm -it -v "%cd%":/root/env myos-buildenv`
 - Windows (PowerShell): `docker run --rm -it -v "${pwd}:/root/env" myos-buildenv`
 - NOTE: If you are having trouble with an unshared drive, ensure your docker daemon has access to the drive you're development environment is in. For Docker Desktop, this is in "Settings > Shared Drives" or "Settings > Resources > File Sharing".

                                          ********Building for x86 architecture:********
                                                      - `make build-x86_64`
  --Then type "exit" to move back to cmd
  
  --Then after successful compilation, type command for EMULATOR QEMU to respond accordingly:
- `qemu-system-x86_64 -cdrom dist/x86_64/kernel.iso`
 - NOTE: When building your operating system, if changes to your code fail to compile, ensure your QEMU emulator has been closed, as this will block writing to `kernel.iso`.

Alternatively, you should be able to load the operating system on a USB drive and boot into it when you turn on your computer. (I haven't actually tested this yet.)

                                                    *************Cleanup*****************

--Remove the build-evironment image:
 - `docker rmi myos-buildenv -f`

