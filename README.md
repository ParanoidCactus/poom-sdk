# POOM
Poom is a remake of Doom for Pico-8. This is a fork of the Poom SDK.

# Poom SDK
For the original SDK and modding documentation see:
https://github.com/freds72/poom-sdk

# Credits
Programming: Frederic Souchu

Art, Level Design & Audio: Simon Hulsinga (Paranoid Cactus)

Based on Original Game by Id Software (Microsoft)

ZDoom Wiki (outstanding content folks!)

# Getting Started
## Pre-Requisites

* [PICO8](ttps://www.lexaloffle.com/pico-8.php) to run game
* [Python 3.6+](https://www.python.org/) to pack levels into pico8 carts

## Install Toolchain
1. Clone repo
2. Open a Python command prompt at repo location
3. (optional) Create a Python virtual env:
    ```shell
    python -m venv env
    sandbox/script/activate
    ```
4. Install WAD compiler:
    ```shell
    pip install tools/wad_reader-<latest version>.tar.gz
    ```
5. Validate install
    ```shell
    python -m wad_reader --help
    ```
    Expected output:
    ```shell
    usage: wad_reader.py [-h] --pico-home PICO_HOME --carts-path CARTS_PATH --mod-name MOD_NAME [--map MAP] [--compress] [--release RELEASE]

    optional arguments:
      -h, --help            show this help message and exit
      --pico-home PICO_HOME
                            Full path to PICO8 folder
      --carts-path CARTS_PATH
                            Path to carts folder where game is exported
      --mod-name MOD_NAME   Game cart name (ex: poom)
      --map MAP             Map name to compile (ex: E1M1)
      --compress            Enable compression (default: false)
      --compress-more       Enable adaptative compression (default: false)
      --release RELEASE     Generate packages (bin+html) with given version
      --sky SKY             Skybox texture name
      --dump-sprites        Writes all sprites to a single image with their 16x16 tile overlay.
      ```

## Compile & Run Poom
1. Open a Python command prompt at repo location (e.g. where DECORATE file is)
2. (optional) Enable Python virtual env
3. Generate a PICO8 multi-cart game with a sample level in carts folder:

```shell
python -m wad_reader --pico-home <path to PICO8> --carts-path <path to carts folder> --mod-name <mod name> --map E1M1
```
Example:
```shell
cd poom-sdk
python -m wad_reader --pico-home d:\pico-8_0.2.0 --carts-path carts --mod-name poom
```

4. Launch game:
```shell
pico8 -home <path to repo> poom_0.p8
```

# Controls

## Mouse + Keyboard

E S D F: move back/forward, strafe left/right

Mouse button 1: fire

Mouse button 2: open door/activate switch

Mouse button 3: switch weapon
  E, S, D, F, MB2: select weapon
  Mouse button 3: pause

## Keyboard Only #1

⬇️⬆️: back/forward

⬅️➡️: turn left/right

🅾️ + ⬅️➡️: strafe

❎: fire

## Keyboard Only #2

> use keyconfig to map second player keys

E S D F: back/forward/strafe

⬅️➡️: turn left/right

❎: fire

## Weapon Selection

pause: open weapon selection wheel

pause: regular pico-8 pause menu

⬇️⬆️⬅️➡️: select weapon
