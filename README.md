# Grubphemous

Grubphemous is a GRUB bootloader theme inspired on Blasphemous's art.

![Grubphemous Theme Preview](/resources/preview.png)

## Installation

1.  **Clone the repository**:
    ```bash
    git clone https://github.com/pvtoari/grubphemous-theme

    cd grubphemous-theme
    ```

2.  **Run the installation script with sudo**:

    The script will prompt you to choose a background and copy the theme files to the appropriate GRUB themes directory.
    ```bash
    sudo ./install_theme.sh
    ```
    This script attempts to copy the theme to `/boot/grub/themes/grubphemous` or `/boot/grub2/themes/grubphemous`.

3.  **Configure GRUB**:
    Edit your GRUB configuration file (usually `/etc/default/grub`) using a text editor:
    ```bash
    sudo nano /etc/default/grub
    ```
    Locate the `GRUB_THEME=` line. If it exists, modify it. If not, add the line. Set it as follows:
    ```ini
    GRUB_THEME="/boot/grub/themes/grubphemous/theme.txt"
    ```
    (If your GRUB directory is `/boot/grub2`, adjust the path to `/boot/grub2/themes/grubphemous/theme.txt`)

4.  **Update GRUB Configuration, e.g.:**
    ```bash
    sudo grub-mkconfig -o /boot/grub/grub.cfg
    ```

## Customization

By default, the background image is provided by `grubphemous/background.png` and set during installation, but if you want to set a different background, you can add your own PNG image to the `background/` directory before running the installation script, or you can change it later manually in the theme's folder e.g.,  `/boot/grub/themes/grubphemous`.

### Background Image

* The `install_theme.sh` script will offer to run the background selection utility during installation.
* You can change the background at any time by running the [`choose_background.sh`](/home/pvtoari/repos/grubphemous-theme/choose_background.sh) script directly from the repo directory:
    ```bash
    ./choose_background.sh
    ```
    After selecting a new background, you will need to re-copy the theme to your GRUB themes directory, or manually copy the updated `grubphemous/background.png` file.
    
* Alternatively, you can manually replace the `grubphemous/background.png` file within the theme's source directory with your desired PNG image and then copy the `grubphemous` folder to `/boot/grub/themes/` (or `/boot/grub2/themes/`).

## TODO
- ~~If possible, add a children of the moonlight cursor at the right of the selection item (like the one in the game)~~ implemented by [@sergoncano](https://github.com/sergoncano), thank you!
- Improve compatibility with other resolutions

## Credits

* ["Blasphemous"](https://fontstruct.com/fontstructions/show/2138043/blasphemous-1) font created by Patrick H. Lauke via Fontstruct.
* The `install_theme.sh` script's structure and some functionalities were inspired by the [minegrub-theme by Lxtharia](https://github.com/Lxtharia/minegrub-theme) repo.
* The game Blasphemous and its art by The Game Kitchen, which served as the inspiration for this theme.

## License

The "Blasphemous" font included in this theme ("Blasphemous" by Patrick H. Lauke) is licensed under the Creative Commons Attribution 3.0 License.

This project is licensed under the MIT license. See the `LICENSE` file for details.
