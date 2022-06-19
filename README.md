# Quantum

External tree for [buildroot](https://buildroot.org) to build firmware image for [Seeed Studio Quantum Mini Linux Development Kit](https://wiki.seeedstudio.com/Quantum-Mini-Linux-Development-Kit/). 

## Working

 * Linux 5.17.3
 * u-boot 2022.04
 * wifi (with iwd)
 * sound
 * leds

## Not working

 * MPU6050
 * TFT Display (DRM_PANEL_SITRONIX_ST7789V)
  
# Building

To build this firmware image, you need to install Buildroot environment and clone this repository as 'external tree' to buildroot. Make sure you check buildroot manual for required packages for your host, before building.

```
mkdir ~/build-directory
cd ~/build-directory
git clone https://git.buildroot.net/buildroot
git clone https://github.com/resiliencetheatre/quantum
```

Define _external tree_ location to **BR2_EXTERNAL** variable:

```
export QUANTUM=~/build-directory/quantum
export BR2_EXTERNAL=${QUANTUM}
```

Make quantum board configuration (defconfig) and start building:

```
cd ~/build-directory/buildroot
make quantum_defconfig
make
```

