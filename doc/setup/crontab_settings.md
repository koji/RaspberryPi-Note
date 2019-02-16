# Crontab

## GUI
```zsh
$ sudo apt-get install gnome-schedule
```

## CLI


```zsh
# * * * * *  command to execute
# ┬ ┬ ┬ ┬ ┬
# │ │ │ │ │
# │ │ │ │ │
# │ │ │ │ └───── day of week (0 - 7) (0 to 6 are Sunday to Saturday, or use names; 7 is Sunday, the same as 0)
# │ │ │ └────────── month (1 - 12)
# │ │ └─────────────── day of month (1 - 31)
# │ └──────────────────── hour (0 - 23)
# └───────────────────────── min (0 - 59)
```

### Create a shellscript
```
$ mkdir TakePhotos
$ cd TakePhotos
$ vim runCamera.sh
```

runCamera.sh
```bash
#!/bin/bash

DATE=$(date +"%Y-%m-%d_%H%M")

#raspistill -vf -hf -o $(pwd)/$DATE.jpg
fswebcam -r 640x480 -F 100 $(pwd)/$DATE.jpg

```

## install fswebcam
```
$ sudo apt-get install fswebcam
```

### Create cron.conf
```
$ echo '* 8 * * * your_shellscript_path' > cron.conf
$ crontab cron.conf
```
