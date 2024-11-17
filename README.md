# riscv-gnu-toolchain-docker-image
Docker image for riscv-gnu-toolchain

It was built with command
```bash
./configure --prefix=/opt/riscv --enable-multilib --enable-qemu-system && \
    make -j$(nproc) newlib linux build-sim SIM=qemu && \
    make install
```

It includes binaries
```
root@docker-desktop:/workspace# ls /opt/riscv/bin/
qemu-edid                       riscv64-unknown-elf-gcov-tool         riscv64-unknown-linux-gnu-gcc-nm
qemu-ga                         riscv64-unknown-elf-gdb               riscv64-unknown-linux-gnu-gcc-ranlib
qemu-img                        riscv64-unknown-elf-gdb-add-index     riscv64-unknown-linux-gnu-gcov
qemu-io                         riscv64-unknown-elf-gprof             riscv64-unknown-linux-gnu-gcov-dump
qemu-nbd                        riscv64-unknown-elf-ld                riscv64-unknown-linux-gnu-gcov-tool
qemu-pr-helper                  riscv64-unknown-elf-ld.bfd            riscv64-unknown-linux-gnu-gdb
qemu-riscv32                    riscv64-unknown-elf-lto-dump          riscv64-unknown-linux-gnu-gdb-add-index
qemu-riscv64                    riscv64-unknown-elf-nm                riscv64-unknown-linux-gnu-gfortran
qemu-storage-daemon             riscv64-unknown-elf-objcopy           riscv64-unknown-linux-gnu-gp-archive
qemu-system-riscv32             riscv64-unknown-elf-objdump           riscv64-unknown-linux-gnu-gp-collect-app
qemu-system-riscv64             riscv64-unknown-elf-ranlib            riscv64-unknown-linux-gnu-gp-display-html
qemu-vmsr-helper                riscv64-unknown-elf-readelf           riscv64-unknown-linux-gnu-gp-display-src
riscv64-unknown-elf-addr2line   riscv64-unknown-elf-run               riscv64-unknown-linux-gnu-gp-display-text
riscv64-unknown-elf-ar          riscv64-unknown-elf-size              riscv64-unknown-linux-gnu-gprof
riscv64-unknown-elf-as          riscv64-unknown-elf-strings           riscv64-unknown-linux-gnu-gprofng
riscv64-unknown-elf-c++         riscv64-unknown-elf-strip             riscv64-unknown-linux-gnu-ld
riscv64-unknown-elf-c++filt     riscv64-unknown-linux-gnu-addr2line   riscv64-unknown-linux-gnu-ld.bfd
riscv64-unknown-elf-cpp         riscv64-unknown-linux-gnu-ar          riscv64-unknown-linux-gnu-lto-dump
riscv64-unknown-elf-elfedit     riscv64-unknown-linux-gnu-as          riscv64-unknown-linux-gnu-nm
riscv64-unknown-elf-g++         riscv64-unknown-linux-gnu-c++         riscv64-unknown-linux-gnu-objcopy
riscv64-unknown-elf-gcc         riscv64-unknown-linux-gnu-c++filt     riscv64-unknown-linux-gnu-objdump
riscv64-unknown-elf-gcc-14.2.0  riscv64-unknown-linux-gnu-cpp         riscv64-unknown-linux-gnu-ranlib
riscv64-unknown-elf-gcc-ar      riscv64-unknown-linux-gnu-elfedit     riscv64-unknown-linux-gnu-readelf
riscv64-unknown-elf-gcc-nm      riscv64-unknown-linux-gnu-g++         riscv64-unknown-linux-gnu-run
riscv64-unknown-elf-gcc-ranlib  riscv64-unknown-linux-gnu-gcc         riscv64-unknown-linux-gnu-size
riscv64-unknown-elf-gcov        riscv64-unknown-linux-gnu-gcc-14.2.0  riscv64-unknown-linux-gnu-strings
riscv64-unknown-elf-gcov-dump   riscv64-unknown-linux-gnu-gcc-ar      riscv64-unknown-linux-gnu-strip
```

You can run it with
```bash
# that will connect your current dir as /workspace
docker run --rm -it --network=host -v .:/workspace riscv-toolchain-multilib:v0.2 bash
```
