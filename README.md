# Swagger ZMK Firmware

This is the ZMK firmware for Swagger, a 12u split keyboard focused on wireless usage.
You can find more info [here](https://github.com/flamwenco/swagger).

## Modifying the keymap
You can edit the keymap in 'config/swagger.keymap' to suit your needs, and then build it with the instructions below.

## Building the firmware with GitHub Actions
### Setup
- Fork this repo.
- Enable GitHub Actions on your fork.

### Build firmware
- Push a commit to trigger the build.
- Download the artifact.

## Flashing the firmware
- Download the 'firmware.zip' artifact from your latest successful Github Actions run for the build.
- Unzip it and you should see a .uf2 file for both the right and left sides.
- Plug the right side into your computer
    - Use tweezers to reset the board, the reset pins on the right side are between N and Space, you should need to tap them together twice
    - Once done, you should see the board mount as a USB device 'NICE_NANO' (or similar if using a different controller) on your computer
    - Open that USB device in your file explorer, and copy the .uf2 for the right side into it
    - Once copied the devie will automatically disconnect and flash itself
- Repeat the above steps with the left side, using the .uf2 for the left side
    - The reset pins on the left side are in the middle of X, C, and Space

Once both sides are flashed, you should be good to go! Pair it to your computer and start typing.

#### Note to user:

- If desired, RGB underglow and encoder support must be manually enabled before building and flashing. Check 'config/swagger.conf' to do so.
- Currently ZMK only supports master side encoders, so only the left side encoder will work.