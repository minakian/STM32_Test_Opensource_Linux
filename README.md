## STM32_Test_Opensource_Linux ##

This project is to test the capabilities of the opensource gcc-arm-none-eabi compiler on the STM32 from a linux machine.

Followed the following instructions to install the compiler:
http://blog.podkalicki.com/how-to-compile-and-burn-the-code-to-stm32-chip-on-linux-ubuntu/

Special note that the following change by "lmbryk" was required:

I solved the problem by adding -c flag in $(CC) $(INCLUDE) $(CFLAGS) $^ -o $@.
Now instruction looks as follow: $(CC) $(INCLUDE) $(CFLAGS) -c $^ -o $@

Also installed newer packages from:
https://packages.ubuntu.com/cosmic/all/libnewlib-dev/download
https://packages.ubuntu.com/cosmic/all/libnewlib-arm-none-eabi/download

and installed using:
sudo dpkg -i libnewlib-dev_2.4.0.20160527-4_all.deb libnewlib-arm-none-eabi_2.4.0.20160527-4_all.deb

* Replace the version number in the command with the downloaded version

The opensource STLink software by Texane can be found at:
https://github.com/texane/stlink

with installation instructions found here:
https://github.com/texane/stlink/blob/master/doc/compiling.md

*Note: I needed to use the system wide command
	$ cd build/Release; sudo make install
to get proper operation.

Contains a very basic MakeFile for compilation, cleaning, and flashing.
