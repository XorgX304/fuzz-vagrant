# fuzz-vagrant

This will install a few fuzzing tools on a Ubuntu Xenial Vagrant Box.

- Install vagrant
- git clone https://github.com/droberson/fuzz-vagrant
- cd fuzz-vagrant
- vagrant up

This VM will provide:
- afl 1.96b from packages
- afl-latest compiled in /opt/afl-VERSION_HERE
- preeny in /opt/preeny
- valgrind from pacages
- gdb
- perf
- ...

