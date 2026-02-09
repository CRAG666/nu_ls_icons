# nu_ls_icons

`nu_ls_icons` is a Nushell script that enhances the standard `ls` command by adding custom icons and colors to file and directory names. This provides a more visually informative and aesthetically pleasing terminal experience.

## Features

- **Iconic Representation:** Easily distinguish between different file types and directories at a glance.
- **Customizable Colors:** Apply custom foreground colors to icons based on file type or directory name.
- **Nushell Integration:** Seamlessly integrates with your existing Nushell environment.

## Installation

### Prerequisites

- [Nushell](https://www.nushell.sh/)

### Steps

1.  **Save the Script:**
    Save the `lsi.nu` file to a convenient location, for example, `~/.config/nushell/lsi.nu`.

    ```bash
    mkdir -p ~/.config/nushell
    cp lsi.nu ~/.config/nushell/lsi.nu
    ```

2.  **Source the Script:**
    Add the following line to your Nushell configuration file (`config.nu`, usually located at `~/.config/nushell/config.nu`) to source the script:

    ```nushell
    source ~/.config/nushell/lsi.nu
    ```

3.  **Create a Theme File (Example):**
    Create a JSON file for your icon theme. For example, `~/.config/nushell/lsi_theme.json`:

    ```json
    {
      "icon": {
        "dirs": [
          { "name": "nu_ls_icons", "text": "󰉋", "fg": "#50fa7b" }
        ],
        "files": [
          { "name": "lsi.nu", "text": "", "fg": "#8be9fd" },
          { "name": "README.md", "text": "", "fg": "#bd93f9" }
        ],
        "exts": [
          { "name": "nu", "text": "", "fg": "#8be9fd" },
          { "name": "md", "text": "", "fg": "#bd93f2" },
          { "name": "png", "text": "", "fg": "#ffb86c" },
          { "name": "json", "text": "", "fg": "#e6e6e6" }
        ]
      }
    }
    ```

4.  **Set the Theme Path:**
    Set the `LSI_THEME_PATH` environment variable in your `config.nu` to point to your theme file:

    ```nushell
    $env.LSI_THEME_PATH = "~/.config/nushell/lsi_theme.json"
    ```

5.  **Alias `ls` (Optional but Recommended):**
    To automatically use the enhanced `ls` command, add this alias to your `config.nu`:

    ```nushell
    alias ls = ls --wrapped
    ```

    *Remember to restart your Nushell session or `source config.nu` for changes to take effect.*

## Usage

Once installed, simply use the `ls` command as you normally would. The output will now include icons and custom colors for files and directories based on your theme configuration.

```bash
ls -la
```

## Screenshots

Here are some examples of `nu_ls_icons` in action:

![Screenshot 1](.show_case/2026-02-08-171258_hyprshot.png)
![Screenshot 2](.show_case/2026-02-09-001532_hyprshot.png)
![Screenshot 3](.show_case/2026-02-09-001546_hyprshot.png)
![Screenshot 4](.show_case/2026-02-09-001617_hyprshot.png)
