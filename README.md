# bitcoin-lemmy
Bitcoin Lemmy instance in Docker


## URL, Hosting & Docker Setup
Instance is located at bitcoinlemmy.com 

This lemmy is hosted on a cloud server using docker and nginx. 

The docker setup we will be using is the jwilder nginx reverse proxy 

## Initial Setup

### Create a Docker folder in your vps
1. SSH in to your VPS
2. make 'docker' folder: `mkdir ~/docker` 
3. make 'lemmy' subfolder: `mkdir ~/docker/lemmy/` 
4. make 'reverse-proxy' subfolder: `mkdir ~/docker/reverse-proxy`

### Create scripts to update VPS 

1. Create a script to transfer to and from the vps `nano sync-from-vps.sh`

    paste this in sync-from-vps.sh:
    ```bash
    #! /bin/bash
    rsync -Pazv -e 'ssh -p [YOURPORT]' --delete root@[YOUR-VPS-IP]:~/docker/* /media/[YOUR-LOCAL-USERNAME]/[YOUR-LOCAL-DEV-FOLDER]
    ```

2. repeat with `nano sync-to-vps.sh`

    paste this in sync-to-vps.sh:
    ```bash
    #! /bin/bash
    rsync -Pazv -e 'ssh -p [YOURPORT]' --delete  /media/[YOUR-LOCAL-USERNAME]/[YOUR-LOCAL-DEV-FOLDER]/* root@[YOUR-VPS-IP]:~/docker/

    ```
3. make each script executable run: `chmod +x sync-to-vps.sh && chmod +x sync-from-vps.sh`

### Setup JWilder reverse proxy docker


