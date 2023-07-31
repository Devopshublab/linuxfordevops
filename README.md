# Steps to setup your linux lab locally
Prerequisite
A. Hardware
  4 (quad core) or more CPUs
  8gb RAM or more 
  50gb or more disk space
B. Softwares
  Windows 10 or higher
  Gitbash
  Oracle virtual box
  Vagrant
Commands to setup your linux lab
  1. Open gitbash and run the below commands
  2. mkdir devopslab
  3. cd devopslab
  4. curl -o Vagrantfile https://raw.githubusercontent.com/devopshubin/linuxfordevops/main/Vagrantfile
  5. vagrant status
  6. vagrant up serverA
