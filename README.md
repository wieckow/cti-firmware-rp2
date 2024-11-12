# Cti-firmware for RP2350 - Raspberry Pi Pico 2 
Note: This is a modified copy of the software available at https://github.com/LabVIEWCommunityTraining/cti-firmwar
The modification allows you to quickly start working with the new version of the RP2350 microcontroller.

## Preparation (at this time Linux only)  
Most Linux distributions come preconfigured with all of the dependencies needed to run the extension. However, some
distributions may require additional dependencies. The extension requires the following:
* Python 3.9 or later
* Git
* Tar
* a native C and C++ compiler (the extension supports GCC) 

You can install these with:
>``$ sudo apt install python3 git tar build-essential``

Git clone this repo

> ``git clone https://github.com/wieckow/cti-firmware-rp2.git``

## Building
Building is accomplished in the linux terminal.

1. Navigate to the rp2040 platform
> ``cd platform\rp2040``
2. Download piko-sdk 
> ``git clone https://github.com/raspberrypi/pico-sdk.git``
3. Create the build folder
> ``mkdir build``
4. Navigate to the build folder
> ``cd build``
5. Configure the build with cmake
> ``cmake -DPICO_PLATFORM=rp2350 -DPICO_BOARD=pico2 ..``
6. Run the build
> ``make``The modification allows you to quickly start working with the new version of the RP2350 microcontroller

With a successful build in a `./build` subdirectory you will have a `cti_visa-udaq_pi_pico_#.#.#.uf2` file that you can deploy to a rp2040 target.

## Testing
> ``screen --version``

If you don’t have screen installed on your system, you can easily install it using the package manager of your distro.
> ``sudo apt install screen``
> ``sudo apt install screen``

Open serial port 
> ``screen /dev/ttyACM0 115200``

The IEEE 488.2 Common Commands (SCPI) are:
> ``*RST - Reset``
> ``*IDN? - Identify``
