# Setting up the TX2

## A Message from a Previous Unfortunate Soul

Steel your nerves, brave adventurers, for you are about to embark on a most-likely harrowing quest. If you've never worked with NVIDIA's developer software before, allow me to be the first to warn you: here there be dragons.

Let's be clear: this guide is *tentative* at best. We're straddling the collision of two hardware providers (NVIDIA, who makes the Jetson TX2, and ConnectTech, who make the Orbitty Carrier we use), who are both hacking together software with the horrifying, rage-inducing results that hardware companies seem uniquely capable of achieving.

## Downloading and Flashing

1. Grab the latest patch for JetPack from ConnectTech [here](http://connecttech.com/support/resource-center/nvidia-jetson-tx2-tx1-product-support/), under "Board Support Packages"/"Looking for board support packages for your TX2 solution?"
1. Download the [JetPack SDK Manager](https://developer.nvidia.com/embedded/jetpack) from NVIDIA. You'll need to make an NVIDIA developer account because they're soul-sucking vampires, presumably.
1. Open the SDK Manager. Login with the same developer account, and select "Jetson TX2 (P3310)" for your Target Hardware, and JetPack 4.2.2. Try to get the package downloaded, but don't bother flashing.

The next steps are loosely taken from [this support page](http://connecttech.com/resource-center/cti-l4t-nvidia-jetson-board-support-package-release-notes/), under *CTI-L4T BSPs for TX2 and TX2i [L4T V32.1.0 and Higher CTI-L4T-V1XX)*. I say loosely because they don't work as written. I know, life is full of disappointment, right?

Instead, try the following:

1. Connect the board to the computer with a USB cable and get it into Recovery mode:
    1. Hold RECOVERY
    1. Press RESET
    1. Wait 2 seconds, then release RECOVERY
1. Run `lsusb` and make sure you see a device named `NVidia`
1. Extract the contents of what you downloaded in step 1 (should be a directory named `CTI-L4T`) above to `~/nvidia/nvidia_sdk/JetPack_4.2_Linux_P3310/Linux_for_Tegra/`, substituting versions and what-not as necessary
1. Go into the directory you just copied and run `sudo ./install.sh`
1. Now go up a directory and run `sudo ./flash.sh cti/tx2/orbitty mmcblk0p1`
1. See if it's willing to boot, and cry when it doesn't

Pro tip: use the small 7-in screen to test if it boots. Otherwise you might waste an ungodly amount of time looking at a black screen on one of the other monitors that it will refuse to boot to.